A stateful set of all reflection instances of a concept

**Example:**

**How to use:**

Create classes for DI that are named after the plural of the concept:

```php
# /trees/Trees.php
class Trees {
  use Set;
  
  public function __construct(
	  protected Database $db
  ) {
  }
  
  public function getAll(): array {
	  
  }
}
```
If a set class becomes very big, extract its related methods into a Repository and inject the repository