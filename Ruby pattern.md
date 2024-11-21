# Ruby Regular Expressions (Regex) Guide

## Basic Regex Creation

In Ruby, regular expressions are created between slashes (`/`) or using `%r{}`:

```ruby
pattern = /ruby/
pattern_alt = %r{ruby}
```

## Regex Matching Operators and Methods

### =~ (Match Operator)
Checks if a pattern matches a string and returns the position of the first match:

```ruby
puts "I love Ruby!" =~ /Ruby/  # Outputs: 7
puts "Hello" =~ /Ruby/         # Outputs: nil
```

### .match Method
Returns a MatchData object with match details:

```ruby
result = /Ruby/.match("I love Ruby!")
puts result[0]     # Outputs: Ruby
```

### .scan Method
Finds all occurrences of the pattern:

```ruby
puts "I love Ruby and Ruby on Rails!".scan(/Ruby/)
# Outputs: ["Ruby", "Ruby"]
```

### .sub and .gsub Methods
- `.sub` replaces the first occurrence
- `.gsub` replaces all occurrences

```ruby
puts "I love Ruby".sub(/Ruby/, "Python")    
# Outputs: I love Python

puts "Ruby is great. Ruby is fun.".gsub(/Ruby/, "Python")
# Outputs: Python is great. Python is fun.
```

## Regex Quantifiers and Special Characters

### Anchors
- `^`: Matches the start of a line
- `$`: Matches the end of a line

```ruby
"Ruby".match(/^R/)  # Matches only if the string starts with 'R'
```

### Quantifiers
- `*`: 0 or more occurrences
- `+`: 1 or more occurrences
- `?`: 0 or 1 occurrence

```ruby
"Ruby!".match(/u*/)    # Matches 0 or more 'u'
"Ruby".match(/u+/)     # Matches 1 or more 'u'
"Ruby".match(/u?/)     # Matches 0 or 1 'u'
```

### Character Classes
- `\d`: Matches any digit (0-9)
- `\w`: Matches word characters (alphanumeric + underscore)
- `\s`: Matches whitespace

```ruby
"123".match(/\d+/)        # Matches "123"
"ruby_123".match(/\w+/)   # Matches "ruby_123"
" ".match(/\s/)           # Matches whitespace
```

## Regex Groups

Use parentheses `()` to create capture groups:

```ruby
pattern = /(\w+)@(\w+)\.(\w+)/
result = pattern.match("user@example.com")
```

## Practical Examples

### Example 1: Basic Pattern Matching
```ruby
text = "hello world"
if text =~ /world/
  puts "Found 'world' in the text"
else
  puts "'world' not found in the text"
end
```

### Example 2: Extracting Numbers
```ruby
text = "I have 2 apples and 3 bananas."
numbers = text.scan(/\d+/)
puts "Extracted numbers: #{numbers}" 
# Output: ["2", "3"]
```

### Example 3: Finding Words
```ruby
text = "Ruby is a beautiful language!"
words = text.scan(/\b\w+\b/)
puts "Words: #{words}" 
# Output: ["Ruby", "is", "a", "beautiful", "language"]
```

### Example 4: Phone Number Validation
```ruby
phone = "123-456-7890"
if phone =~ /^\d{3}-\d{3}-\d{4}$/
  puts "Valid phone number format"
else
  puts "Invalid phone number format"
end
```

### Example 5: Removing Vowels
```ruby
text = "Hello, Ruby!"
no_vowels = text.gsub(/[aeiouAEIOU]/, "")
puts no_vowels 
# Output: "Hll, Rby!"
```

## Key Takeaways
- Regex provides powerful string manipulation
- Use `/pattern/` or `%r{pattern}` to create regex
- Multiple methods like `=~`, `.match`, `.scan`, `.sub`, `.gsub`
- Quantifiers and character classes offer flexible matching
- Capture groups help extract specific parts of a match
