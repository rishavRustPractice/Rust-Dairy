# BTree Map

```rust
use std::collections::BTreeMap;

struct Db {
    elements: BTreeMap<String, String>
}
impl Db {
    fn insert(&mut self, key: String, value: String) {
        self.elements.insert(key, value);
    }
    fn find_one(self, key: String) -> String {
        let res = self.elements
            .get(&key)
            .unwrap();
        res.to_string()
    }
}

fn new_db() -> Db{
    Db {
        elements: BTreeMap::new(),
    }
}

fn main() {
    println!("Rust BTreeMap implementation");
    let mut db: Db = new_db();
    db.insert("Hello".to_string(), "World".to_string());
    println!("{}", db.find_one("Hello".to_string()));
}

```
