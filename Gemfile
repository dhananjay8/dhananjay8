source "https://rubygems.org"

# Match the GitHub Pages build environment (includes jekyll-feed, jekyll-seo-tag, jekyll-sitemap)
gem "github-pages", group: :jekyll_plugins

group :test do
  gem "html-proofer", "~> 5.0"
end

# Windows and JRuby does not include zoneinfo files
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
