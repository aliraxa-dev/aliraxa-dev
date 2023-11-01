class Console
  COLORS = {
    black: 30,
    red: 31,
    green: 32,
    yellow: 33,
    blue: 34,
    pink: 35,
    light_blue: 36,
    white: 37,
    light_grey: 90,
    dark: 40,
    alert: 41,
    success: 42,
    info: 43,
    primary: 44,
    warning: 45,
    help: 46,
    log: 47
  }.freeze

  COLORS.each do |color, code|
    define_method(color) do |text|
      puts "\e[#{code}m#{text}\e[0m"
    end
  end
end

console = Console.new
console.info('Terminal Colores are working!')

## To use this in ruby irb session
- Downlaod this file
- Place in the directory where you want
- rename the file
```
mv terminal-colors.md terminal-colors.rb
```
- require this file in the irb session like this
```
require "~/path/terminal-colors.rb"
```
- create the instance of the class
```
console = Console.new
```
- Now you can use it like that
```
console.black("Black text")
console.dark("text with black background")
```
