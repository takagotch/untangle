### untangle
---
https://github.com/stchris/untangle

```py
// tests/test.py

class PrserFeatureTestCase(unittest.TestCase):
  
  bad_dtd_xml = """
  """
  
  def test_valid_feature(self):
  
  def test_inalid_feature(self):
  
  def test_invalid_external_dtd(self):
    with self.assertRaises(IOError):
      untangle.parse(self.bad_dtd_xml, feature_external_ges=True)
      
if __name__ == '__main__':
  unittest.main()
```

```
```

```
```


