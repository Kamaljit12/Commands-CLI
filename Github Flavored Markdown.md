# Heading

    # Sample H1
    ## Sample H2
    ### Sample H3

# Horizontal rule is created using --- on a line by itself.
    Horizontal rule
    ---
 
 ## result
 
 Horizontal rule
  ---
# Coding - Block

    ```ruby
    # The Greeter class
    class Greeter
      def initialize(name)
        @name = name.capitalize
      end
    
      def salute
        puts "Hello #{@name}!"
      end
    end
    
    # Create a new object
    g = Greeter.new("world")
    
    # Output "Hello World!"
    g.salute
    ```
## result

```ruby
# The Greeter class
class Greeter
  def initialize(name)
    @name = name.capitalize
  end

  def salute
    puts "Hello #{@name}!"
  end
end

# Create a new object
g = Greeter.new("world")

# Output "Hello World!"
g.salute
```
Note: You can specify the different syntax highlighting based on the coding language eg. ruby, sh (for shell), php, etc
Note: You must leave a blank line before the \```

# Coding - In-line
You can produce inline-code by using only one ` to enclose the code:

    This is some code: `echo something`

##  result
This is some code: `echo something`

# Text Formatting
    Bold Text is done using **Bold Text**
    Italic Text is done using *Italic Text*

## result

Bold Text is done using **Bold Text**

Italic Text is done using *Italic Text*

# Hyperlinks
- GFMD will automatically detect URL and convert them to links like this http://www.futureworkz.com
- To specify a link on a text, do this:

      This is [an example](http://example.com/ "Title") inline link.
      [This link](http://example.net/) has no title attribute.

## result

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

# Escape sequence
    You can escape using \ eg. \`

## result
You can escape using \ eg. \`

# Creating list
Adding a - will change it into a list:

    - Item 1
    - Item 2
    - Item 3
## Result

- Item 1
- Item 2
- Item 3

# Quoting
You can create a quote using >:

    > This is a quote

# result
> This is a quote

# Table and Definition list
These two can only be created via HTML:

    <table>
      <tr>
        <th>ID</th><th>Name</th><th>Rank</th>
      </tr>
      <tr>
        <td>1</td><td>Tom Preston-Werner</td><td>Awesome</td>
      </tr>
      <tr>
        <td>2</td><td>Albert Einstein</td><td>Nearly as awesome</td>
      </tr>
    </table>
    
    <dl>
      <dt>Lower cost</dt>
      <dd>The new version of this product costs significantly less than the previous one!</dd>
      <dt>Easier to use</dt>
      <dd>We've changed the product so that it's much easier to use!</dd>
    </dl>
    ```
    
    will produce
    
    <table>
      <tr>
        <th>ID</th><th>Name</th><th>Rank</th>
      </tr>
      <tr>
        <td>1</td><td>Tom Preston-Werner</td><td>Awesome</td>
      </tr>
      <tr>
        <td>2</td><td>Albert Einstein</td><td>Nearly as awesome</td>
      </tr>
    </table>
    
    <dl>
      <dt>Lower cost</dt>
      <dd>The new version of this product costs significantly less than the previous one!</dd>
      <dt>Easier to use</dt>
      <dd>We've changed the product so that it's much easier to use!</dd>
    </dl>
    ## Adding Image
    ```
    ![Branching Concepts](http://git-scm.com/figures/18333fig0319-tn.png "Branching Map")
    ```

    

## result 

<table>
  <tr>
    <th>ID</th><th>Name</th><th>Rank</th>
  </tr>
  <tr>
    <td>1</td><td>Tom Preston-Werner</td><td>Awesome</td>
  </tr>
  <tr>
    <td>2</td><td>Albert Einstein</td><td>Nearly as awesome</td>
  </tr>
</table>

<dl>
  <dt>Lower cost</dt>
  <dd>The new version of this product costs significantly less than the previous one!</dd>
  <dt>Easier to use</dt>
  <dd>We've changed the product so that it's much easier to use!</dd>
</dl>
```

will produce

<table>
  <tr>
    <th>ID</th><th>Name</th><th>Rank</th>
  </tr>
  <tr>
    <td>1</td><td>Tom Preston-Werner</td><td>Awesome</td>
  </tr>
  <tr>
    <td>2</td><td>Albert Einstein</td><td>Nearly as awesome</td>
  </tr>
</table>

<dl>
  <dt>Lower cost</dt>
  <dd>The new version of this product costs significantly less than the previous one!</dd>
  <dt>Easier to use</dt>
  <dd>We've changed the product so that it's much easier to use!</dd>
</dl>
## Adding Image
```
![Branching Concepts](http://git-scm.com/figures/18333fig0319-tn.png "Branching Map")
```

# The table in your example can also be produced with:

    ID | Name | Rank
    -- | ---- | ----
    1 | Tom Preston-Werner | Awesome
    2 | Albert Einstein | Nearly as awesome

# RESULT
ID | Name | Rank
-- | ---- | ----
1 | Tom Preston-Werner | Awesome
2 | Albert Einstein | Nearly as awesome



