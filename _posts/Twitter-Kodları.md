Kodları son kontrol tarihi 05.09.2017 hiç birinde sorun yok . ( Sorun bulmanız halinde iletişime geçiniz )

Twitter Toplu Takip Etme Kodu

var say=0,limit=1e3,takipyap=setInterval
(function(){return $(".following").each(function()
{$(this).parents(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").remove()}),
$(".GridTimeline").find("div.not-following > .js-follow-btn>button").first()
.click(),say++>=limit?(clearInterval(takipyap),
window.alert(limit+" kisi basariyla takip edildi."),!1):void $(".message-text > a")
.each(function(){"46px"===$(".alert-messages").css("top")&&(clearInterval(takipyap),
clearInterval(asagi))})},1e3),asagi=setInterval(function(){var a=$(".GridTimeline").
find(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").length;54>=a&&($(".Grid.Grid--withGutter")
.each(function(){0==$(this).children().length&&$(this).remove()}),$(window).scrollTop
(0,document.body.scrollBottom),setTimeout(function(){window.scrollTo(0,document.body.scrollHeight)}
,2000))},2e3);

Twitter Toplu Takip Bırakma Kodu

setInterval(function () {
t = $(".following").find(".follow-button");
if (!t[0]) {
window.scrollTo(0, $(document).height());
} else {
console.log(t.attr("class"));
t.trigger("click");
}
}, 2000)

Twitter Takip Etmeyenleri Takip Bırakma Kodu

setInterval(function() {
$(".FollowStatus").each(function(){
$(this).parents(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").remove();
});
$("div:not(.not-following) > .user-actions-follow-button").click();
}, 20000);
setInterval(function() {
$(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").remove();
}, 30000);
setInterval(function() {
window.scrollTo(0,document.body.scrollBottom);
},5000);
setInterval(function() {
window.scrollTo(0,document.body.scrollHeight);
},2000);

Twitter Toplu Twit Silme Kodu

var kac_tweet_atla = 1;
setInterval(function() {
setTimeout(function(){
$(".Icon.Icon--small.Icon--retweeted").parents(".js-stream-item.stream-item.stream-item").remove()
$(".stream-item").find(".js-actionDelete > button")[kac_tweet_atla].click();
},1000)
setTimeout(function(){
$(".modal.draggable#delete-tweet-dialog-dialog button.btn.primary-btn.delete-action").click();
},1000)
},2000)
setInterval(function() {
window.scrollTo(0,document.body.scrollBottom);
},10000);
setInterval(function() {
window.scrollTo(0,document.body.scrollHeight);
},2000);

Twitter Toplu Sessize Alma Kodu

setInterval(function(){
var kullanc = $(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").length;
if(kullanc >= 18){
var usid = $(".GridTimeline").find(".js-stream-item:first-child").attr("data-item-id")
var token = $("#signout-form > input.authenticity_token").attr('value');
$.ajax({
type: "POST",
url: "https://twitter.com/i/user/mute",
data: {authenticity_token: token, user_id: usid, impression_id:""},
});
$(".GridTimeline").find(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10")[0].remove()
}
},100);
kisiyukle = setInterval(function(){
var kullanc = $(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").length;
if(kullanc <= 54){
$(window).scrollTop(0,document.body.scrollBottom);
setTimeout(function(){
window.scrollTo(0,document.body.scrollHeight);
},200);
}
if($(".GridTimeline").find(".GridTimeline-items").attr("data-min-position") == 0){
$(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").each(function(){
$(this).find(".user-dropdown.dropdown-toggle.js-dropdown-toggle.js-link.js-tooltip.btn.plain-btn.small-user-dropdown").click()
$(this).find(".mute-user-item> button").click();
$(this)[0].remove();
});
clearInterval(sessizeal);
clearInterval(kisiyukle);
$(".bird-topbar-etched").click();
}
},1600)

Toplu Geri Takip Kodu

var kul_adi = prompt("Bir kullaniciya kadar takip etmek icin takip etmediginiz bir kullanici adini basinda @ olmadan girin. Bu secenegi kullanmak istemiyorsaniz bos birakin ya da iptal edin", "");
geritakip = setInterval(function(){
	$(".following, .pending").parents(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").remove();
	$('div.not-following > button.js-follow-btn').each(function(){
		$(this).click();
			if(kul_adi == $(this).parents(".ProfileCard.js-actionable-user").attr("data-screen-name")){
			clearInterval(geritakip);
			clearInterval(yu);
			clearInterval(as);
			alert(kul_adi + "kullanici adina kadar geri takip yapildi.")
		}
		$(".message-text > a").each(function(){
			if ($('.alert-messages').css('top') === '46px'){
				clearInterval(geritakip);
				clearInterval(yu);
				clearInterval(as);
				alert("Takip limitiniz doldu. Bugun daha fazla takip yapamazsiniz.")
			}
		})
	});
	setTimeout(function() {
		$(".Grid.Grid--withGutter[data-component-term='user'], ProfileClusterFollow").remove();
	},1000);
},2000);
var yu = setInterval(function() {
window.scrollTo(0,document.body.scrollHeight);
},1000);
var as = setInterval(function() {
window.scrollTo(0,document.body.scrollBottom);
},2020);

Toplu Dm Kodu
( 2. satırda ki 10 yazan yer , kaç kişiye mesaj atacağınızdır . 100 kişiye mesaj atacaksanız 10 yerine 100 yazmalısınız . Son satırda yer alan 1000 yazan yer 0’a yaklaştıkça mesaj atmanız hızlanır fakat 1000 olarak kalması önerilir . )


var dmbs = 0;
var dmlimit = 10;
var dmdm = setInterval(function(){
 if(dmbs++ >= dmlimit){
 clearInterval(dmdm);
 clearInterval(as);
 clearInterval(yu);
 window.alert(dmlimit+' kisiye mesaj basariyla gonderildi.')
 return false;
 }
 $(".user-dropdown.dropdown-toggle")[0].click();
 $(".mention-text > button")[0].click();
 var dmler = new Array()
 dmler[0] = "Takip icin tesekkur ederim efendim.";
 dmler[1] = "Beni takip etmissiniz. Tesekkurler.";
 dmler[2] = "Takip listenize eklediginiz icin tesekkur ederiz";
 dmler[3] = "Tesekkurler, takipte kalmaniz dilegiyle.";
 dmler[4] = "Tesekkurler yeni takipcim.";
 dmler[5] = "Takibe deger gordugunuz icin tesekkurler.";
 dmler[6] = "Her ne sebeple taqip ettiyseniz tesekurler.";
 dmler[7] = "Takipte kalmaniz dilegiyle sagolun.";
 dmler[8] = "Tesekkurler iyi takipler.";
 dmler[9] = "Takip icin sagolun.";
 var i = Math.floor(10*Math.random());
 var ka = $(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10").find(".ProfileCard.js-actionable-user").attr('data-screen-name');
 document.getElementById("tweet-box-global").innerHTML = "m @"+ka+" "+dmler[i]+"";
 setTimeout(function(){
 $(".btn.primary-btn.tweet-action.tweet-btn.js-tweet-btn.messaging").click();
 },2000);
 $(".Grid-cell.u-size1of2.u-lg-size1of3.u-mb10")[0].remove();
},5000)
var as = setInterval(function() {
 $(window).scrollTop(0,document.body.scrollBottom);
},1000);
var yu = setInterval(function() {
 window.scrollTo(0,document.body.scrollHeight);
},1000)

Twitter Mesajları Silme Kodu

 1
var kac_mesaj_atla = "0";
2
tum_dm_sil = setInterval(function(){
3
$(".DMInbox > li > .DMInboxItem")[kac_mesaj_atla].click(); 
4
$(".u-textUserColorHover.dropdown-toggle.js-tooltip.js-dropdown-toggle")[0].click();
5
$(".dm-conversation-actions").find(".js-actionDeleteConversation>button.dropdown-link")[0].click();
6
if($("#confirm_dialog").css("display") === "block"){
7
$("#confirm_dialog_submit_button")[0].click(); 
8
$("#confirm_dialog").addClass("visuallyhidden"); 
9
}
10
},1000);

Twitter Fav Sıfırlama Kodu

setInterval(function(){
$(".ProfileTweet-actionButton.js-actionFavorite")[0].click()
 $('.stream-items > .js-stream-item.stream-item.stream-item')[0].remove();
},300);
setInterval(function() {
 $(window).scrollTop(0,document.body.scrollBottom);
},1500);
setInterval(function() {
 window.scrollTo(0,document.body.scrollHeight);
},1000);

