# widget-caption
The dataset includes widget captions that describes UI element's functionalities. It is used for training and evaluation of the widget captioning model (please see the EMNLP'20 paper: https://arxiv.org/abs/2010.04295).

Notice that among all the 61,286 widgets with released captions, 12,960 of them (datasetId=nr) rely on internally collected screens (as described in the paper). Although these captions are included in the dataset, their screens are not released due to copyrights.

The widget can be found using the `nodeId` field, as shown below.

```python
index_list = row['nodeId'].split('.')[1:]
index_list = [int(i) for i in index_list]
with open('SCREEN_ID.json') as f:
  view = json.load(f)
curr_node = view['activity']['root']
for index in index_list:
  curr_node = curr_node['children'][index]
```

License: the dataset is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

Please visit https://github.com/google-research/google-research/tree/master/widget_caption for model codes.
