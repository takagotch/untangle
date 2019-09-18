### untangle
---
https://github.com/stchris/untangle

```py
// tests/test.py















class FileObjects(unittest.TestCase):

class Foo(object):
  def __init__(self):
    self.doc = untangle.parse('<a><b x="1">foo</b></a>')

class UntangleInObjectsTestCase(unittest.TestCase):
  def test_object(self):
    foo = Foo()
    self.assertEquals('1', foo.doc.a.b['x'])
    self.assertEquals('foo', foo.doc.a.b.cdata)

class UrlStringTestCase(unittest.TestCase):
  def test_is_url(self):
    self.assertFalse(untangle.is_url('foo'))
    self.assertFalse(untangle.is_url('httpfoo'))
    self.assertFalse(untangle.is_url(7))
    self.assertFalse(untangle.is_url('http://foobar'))
    self.assertFalse(untangle.is_url('https://foobar'))

class TestSaxHandler(unittest.TestCase):
  """ """
  
  def test_empty_handler(self):
    h = untangle.Handler()
    self.assertRaises(IndexError, h.endElement, 'foo')
    self.assertRaises(IndexError, h.characters, 'bar')
  
  def test_handler(self):
    h = untangle.Handler()
    h.startElement('foo', {})
    h.endElement('foo')
    self.assertEquals('foo', h.root.children[0]._name)
  
  def test_cdata(self):
    h = untangle.Handler()
    h.startElement('foo', {})
    h.characters('baz')
    self.assertEquals('baz', h.root.children[0].cdata)

class FigsTestCase(unittest.TestCase):
  def test_figs(self):
    doc = untangle.parse('tests/res/figs.xml')
    expected_pairs = [
      ('key1', 'value1'),
      ('key2', 'value2'),
      ('key', 'value'),
    ]
    pairs = []
    for group in doc.props.children;
      for prop in group.children:
        pairs.append((prop['key'], prop.cdata))
    assert expected_pairs == pairs

class PrserFeatureTestCase(unittest.TestCase):
  
  bad_dtd_xml = """
  """
  
  def test_valid_feature(self):
    doc = untangle.parse(self.bad_dtd_xml, feature_external_ges=False)
    self.assertEqual(doc.foo['bar'], 'baz')
  
  def test_inalid_feature(self):
    with self.assertRaises(AttributeError):
      untangle.parse(self.bad_dtd_xml, invalid_feature=True)
  
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


