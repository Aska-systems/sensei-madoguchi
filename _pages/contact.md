---
title: "Contact"
permalink: "/contact.html"
---

<form id="googleform" method="post" action="https://docs.google.com/forms/u/1/d/e/1FAIpQLSe8tkQdzpM7D1Y1L1PsNR6_p7u7dJh3XIrrUQOBei-WXgwj2w/formResponse">    
<p>弊社サービスやプロダクトについてのご質問やご相談などは、こちらにて承っております。</p>
<!-- <p class="mb-4">Please send your message to {{site.name}}. We will reply as soon as possible!</p> -->
<div class="form-group row">
<div class="col-md-6">
<input class="form-control" type="text" id="name" name="entry.571957993" placeholder="ご所属・お名前*" required>
</div>
<div class="col-md-6">
<input class="form-control" type="email" id="email" name="entry.339748413" placeholder="Eメールアドレス*" required>
</div>
</div>
<textarea rows="8" class="form-control mb-3" id="message" name="entry.1890939504" placeholder="お問合せ内容*" required></textarea>    

<div class="success-message">
	<h3 class="mb-4 text-primary"><i class="fa fa-check"></i> 送信完了しました</h3>
	<p>折り返し返信いたしますので、お待ちください。</p>
</div>
<div class="failure-message">
	<h3 class="mb-4 text-danger">送信できませんでした</h3>
	<p>お手数ですが、contact@aska.systems宛に送信いただけますと幸いです。</p>
</div>

<input class="btn btn-success" type="submit" value="送信">
</form>


<script>
$(document).ready(function () {

      $('#googleform').submit(function (event) {
        var formData = $('#googleform').serialize();
        $.ajax({
          url: "https://docs.google.com/forms/u/1/d/e/1FAIpQLSe8tkQdzpM7D1Y1L1PsNR6_p7u7dJh3XIrrUQOBei-WXgwj2w/formResponse",
          data: formData,
          type: "POST",
          dataType: "xml",
          statusCode: {
            0: function () {
              $(".success-message").slideDown();
              $(".btn-submit").fadeOut();
              //window.location.href = "thanks.html";
            },
            200: function () {
              $(".failure-message").slideDown();
            }
          }
        });
        event.preventDefault();
      });

    });
</script>
