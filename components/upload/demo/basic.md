# 点击上传

- order: 0

经典款式，用户点击按钮弹出文件选择框。

---

````jsx
var Upload = antd.Upload;
var message = antd.message;

var props = {
  name: 'file',
  action: '/upload.do',
  onChange(info) {
    if (info.file.status !== 'uploading') {
      console.log(info.file, info.fileList);
    }
    if (info.file.status === 'done') {
      message.success(info.file.name + ' 上传成功。');
    } else if (info.file.status === 'error') {
      message.error(info.file.name + ' 上传失败。');
    }
  }
};

React.render(
  <Upload {...props}>
    <button type="button" className="ant-btn ant-btn-ghost">
      <i className="anticon anticon-upload"></i> 点击上传
    </button>
  </Upload>
, document.getElementById('components-upload-demo-basic'));
````
