# Hello
hello-world

// pages/ip/ip.js
Page({
  /**
   * 页面的初始数据
   */
  data: {
    ip: '',
    ipText:''
  },
  /**
   * 设置IP地址
   */
  setIp:function(event){
    console.log(event);
    this.setData({ip:event.detail.value})
  },

  /**
   * 获取IP所对应的地理位置
   */
  getCity:function(){
    console.log(this.data.ip);
    var page = this;
    wx.request({
      url: 'http://ip.taobao.com/service/getIpInfo.php?ip='+this.data.ip,
      success:function(res){
        console.log(res.data)
        var city = res.data.data.city;
        page.setData({ ipText:city})
      }
    })
  },

  /**
   * 生命周期函数--监听页面加载
   */
  onLoad: function (options) {
  
  },

  /**
   * 生命周期函数--监听页面初次渲染完成
   */
  onReady: function () {
  
  },

  /**
   * 生命周期函数--监听页面显示
   */
  onShow: function () {
  
  },

  /**
   * 生命周期函数--监听页面隐藏
   */
  onHide: function () {
  
  },

  /**
   * 生命周期函数--监听页面卸载
   */
  onUnload: function () {
  
  },

  /**
   * 页面相关事件处理函数--监听用户下拉动作
   */
  onPullDownRefresh: function () {
  
  },

  /**
   * 页面上拉触底事件的处理函数
   */
  onReachBottom: function () {
  
  },

  /**
   * 用户点击右上角分享
   */
  onShareAppMessage: function () {
  
  }
})
