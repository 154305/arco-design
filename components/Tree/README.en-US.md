`````
Component / Data Display

# Tree

For content with many levels, such as folders, catalogs, and organizational structures, the tree can clearly show their hierarchical relationship, and has interactive functions such as expanding, collapsing, and selecting.
`````

%%Content%%

## API

### Tree

|Property|Description|Type|DefaultValue|Version|
|---|---|---|---|---|
|style|Additional style|`CSSProperties`|`-`|-|
|className|Additional css class|`string \| string[]`|`-`|-|
|size|To set size|`'mini' \| 'small' \| 'default' \| 'large'`|`-`|-|
|blockNode|Whether to occupy the remaining horizontal space|`boolean`|`-`|-|
|autoExpandParent|Whether to automatically expand the parent node|`boolean`|`true`|-|
|multiple|Whether to support multiple selection|`boolean`|`-`|-|
|checkable|Whether to add a checkbox before the node|`boolean`|`-`|-|
|draggable|Whether the node can be dragged|`boolean`|`-`|-|
|allowDrop|Whether to allow dropping on node|`AllowDrop`|`() => true`|2.7.0|
|selectable|Whether can be selected|`boolean`|`true`|-|
|checkStrictly|Whether to cancel the parent-child association|`boolean`|`-`|-|
|checkedStrategy|Customize the return value <br/> all: Return all selected nodes<br/> parent:Only return the parent node when both parent and child nodes are selected <br/> child: Return only child nodes|`SHOW_ALL \| SHOW_PARENT \| SHOW_CHILD`|`all`|-|
|defaultSelectedKeys|The key of node selected by default|`string[]`|`-`|-|
|selectedKeys|The key of the selected node(controlled)|`string[]`|`-`|-|
|defaultCheckedKeys|The key of node checked by default|`string[]`|`-`|-|
|checkedKeys|The key of the checked node(controlled)|`string[]`|`-`|-|
|halfCheckedKeys|the keys of half checked|`string[]`|`-`|2.27.0|
|defaultExpandedKeys|The key of node expanded by default|`string[]`|`-`|-|
|expandedKeys|The key of the expanded node (controlled)|`string[]`|`-`|-|
|treeData|The tree structure can be generated by passing in `treeData`|`TreeDataType[]`|`-`|-|
|fieldNames|Custom field name for key, title, isLeaf, disabled and children|`FieldNamesType`|`-`|2.11.0|
|icons|Customize node icon|`\| ((nodeProps: NodeProps) => {dragIcon?: ReactNode;switcherIcon?: ReactNode;loadingIcon?: ReactNode;})\| {dragIcon?: ReactNode;switcherIcon?: ReactNode;loadingIcon?: ReactNode;}`|`FieldNamesType`|2.9.0|
|virtualListProps|Pass the virtual-list properties, pass in this parameter to turn on virtual scrolling|`AvailableVirtualListProps`|`-`|2.11.0|
|renderExtra|Render additional node|`(props: NodeProps) => ReactNode`|`-`|-|
|renderTitle|Customize title rendering|`(props: NodeProps) => ReactNode`|`-`|-|
|showLine|Whether to display the connection line|`boolean`|`-`|-|
|loadMore|Callback when loaded data asynchronously, returning a `Promise`.|`(node: NodeInstance) => Promise<void>`|`-`|-|
|onSelect|Callback when selected node|`(selectedKeys: string[],extra: {selected: boolean;selectedNodes: NodeInstance[];node: NodeInstance;e: Event;}) => void`|`-`|-|
|onCheck|Callback when checked node|`(checkedKeys: string[],extra: {node: NodeInstance;checkedNodes: NodeInstance[];checked: boolean;halfCheckedKeys: string[]; // version 2.27.0halfCheckedNodes: NodeInstance[]; // version 2.27.0e: Event;}) => void`|`-`|-|
|onExpand|Callback when expanded or collapsed node|`(expandedKeys: string[],exra?: { expanded: boolean; node: NodeInstance; expandedNodes: NodeInstance[] }) => void`|`-`|-|
|onDragStart|Callback when the node starts dragging|`(e: DragEvent<HTMLSpanElement>, node: NodeInstance) => void`|`-`|-|
|onDragEnd|Callback when the node ends drag|`(e: DragEvent<HTMLSpanElement>, node: NodeInstance) => void`|`-`|-|
|onDragOver|Callback when the node is dragged onto a valid target|`(e: DragEvent<HTMLSpanElement>, node: NodeInstance) => void`|`-`|-|
|onDragLeave|Callback when the node leaves a valid target|`(e: DragEvent<HTMLSpanElement>, node: NodeInstance) => void`|`-`|-|
|onDrop|Callback when the node is dropped on the valid target|`(info: {e: DragEvent<HTMLSpanElement>;dragNode: NodeInstance \| null;dropNode: NodeInstance \| null;dropPosition: number;}) => void`|`-`|-|

### Tree.Node

|Property|Description|Type|DefaultValue|
|---|---|---|---|
|style|Additional style|`CSSProperties`|`-`|
|className|Additional css class|`string \| string[]`|`-`|
|title|Title for node|`string \| ReactNode`|`-`|
|selectable|Whether it can be selected|`boolean`|`true`|
|disabled|Whether to disable node|`boolean`|`-`|
|disableCheckbox|Whether to disable check|`boolean`|`-`|
|icon|Custom icon|`ReactNode`|`-`|
|checkable|Whether to show checkbox|`boolean`|`-`|
|isLeaf|Is it a leaf node. Effective when loading dynamically|`boolean`|`-`|
|icons|Customize node icons, it have higher priority than Tree. When the icons property on the Tree is set at the same time, will be merged.|`TreeProps['icons']`|`-`|
|draggable|Whether the current node can be dragged|`boolean`|`-`|

### VirtualListProps

|Property|Description|Type|Default|
|---|:---:|:---:|---:|
|height|Viewable area height (`2.11.0` starts to support `string` type such as `80%`)|`number`| `200` |
|threshold|The threshold of the number of elements that automatically enable virtual scrolling, pass in `null` to disable virtual scrolling.|`number` \| `null`| `100` |
|isStaticItemHeight|Whether it is a static element of the same height|`boolean`|`true`|


FieldNamesType

```js
type FieldNamesType = {
  // Specify the key corresponding to the field in treeData
  key?: string;
  // Specify the corresponding field of title in treeData
  title?: string;
  disabled?: string;
  children?: string;
  isLeaf?: string;
  disableCheckbox?: string;
  checkable?: string;
};
```
