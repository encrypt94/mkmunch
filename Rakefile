require 'yaml'
require 'liquid'
require 'fileutils'

task :generate, [:deck] do |t, args|
  deck = YAML.load_file(args[:deck])
  if !deck.has_key?("layout") || !File.exists?("./_layouts/"+deck["layout"]+".html")
    puts "Layout not found"
    next
  end
  layout = File.open("_layouts/"+deck["layout"]+".html","r").read()
  tpl = Liquid::Template.parse(layout)
  Dir.mkdir("./_cards") unless Dir.exists?("./_cards")
  if deck.has_key?("cards")
    deck["cards"].each do |card|
      puts "Processing "+card["name"]
      filename = card["name"].downcase.gsub(" ","-")
      File.write("./"+filename+".html", tpl.render(card))
      `wkhtmltoimage --enable-local-file-access --transparent #{filename}.html _cards/#{filename}.png`
      `convert -trim _cards/#{filename}.png _cards/#{filename}.png`
      File.delete("./"+filename+".html")
    end
  end
end

task :clean do
  FileUtils.rm_r("./_cards", force: true)
end
