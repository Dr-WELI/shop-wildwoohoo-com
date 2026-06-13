source "https://rubygems.org"

# Pinned to the github-pages gem so local builds match GitHub Pages' build
# exactly. Update via `bundle update github-pages` if GitHub Pages updates.
# Reference: https://pages.github.com/versions/
# Local builds need Ruby 3.x; the system Ruby 2.6 cannot build this site.
# Verify on the GitHub Pages build after push.
gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-sitemap"
end

# Performance booster (Jekyll suggestion)
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]
gem "tzinfo-data", :platforms => [:mingw, :x64_mingw, :mswin, :jruby]
