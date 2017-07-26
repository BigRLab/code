###OrderedMultiDict and UnorderedMultiDict

Originally published: 2003-01-09 16:13:57
Last updated: 2003-01-09 16:13:57
Author: Andrew Dalke

This implements two types of dictionary-like objects where there can be more than one entry with the same key. One is OrderedMultiDict, which preserves the order of all entries across all keys. The other is UnorderedMultidict, which only preserves the order of entries for the same key.\n\nDownload MultiDict.py\nExample:\n>>> import MultiDict\n>>> od = MultiDict.OrderedMultiDict()\n>>> od["Name"] = "Andrew"; od["Color"] = "Green"\n>>> od["Name"] = "Karen"; od["Color"] = "Brown"\n>>> od["Name"]\n'Karen'\n>>> od.getall("Name")\n['Andrew', 'Karen']\n>>> for k, v in od.allitems():\n...     print "%r == %r", (k, v)\n...\n'Name' == 'Andrew'\n'Color' == 'Green'\n'Name' == 'Karen'\n'Color' == 'Brown'\n>>> ud = MultDict.UnorderedMultiDict(od)\n>>> for k, v in ud.allitems():\n...     print "%r == %r", (k, v)\n...\n'Name' == 'Andrew'\n'Name' == 'Karen'\n'Color' == 'Green'\n'Color' == 'Brown'\n>>>