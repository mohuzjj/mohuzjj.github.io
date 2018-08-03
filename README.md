<!DOCTYPE html>
<html>

	<head>
		<meta charset="utf-8">
		<title>My test page</title>
	</head>

	<body>
		<img src="images/myimage.jpg" alt="My test image" />
		<h1>my test page</h1>
		<button>更改用户</button>

		<script>
			var img = document.querySelector('img');

			img.onclick = function() {
				src = img.getAttribute('src');
				if(src === 'images/myimage.jpg') {
					img.setAttribute('src', 'images/timg.jpg');
				} else {
					img.setAttribute('src', 'images/myimage.jpg');
				}
			}

			var myButton = document.querySelector('button');
			var myHeading = document.querySelector('h1');

			function setUserName() {
				var myName = prompt('请输入你的名字！');
				localStorage.setItem('name', myName);
				myHeading.textContent = 'Mozilla很酷，' + myName + '!';
				if(!localStorage.getItem('name')) {
					setUserName();
				} else {
					var storedName = localStorage.getItem('name');
					myHeading.textContent = 'Mozilla很酷，' + storedName + '!';
				}
			}

			myButton.onclick = function() {
				setUserName();
			}
		</script>
	</body>

</html>
