<form>
  <input type="text">
  <button class="submit-btn" type="button">Submit</button>
</form>


<style>
  form {
	display: flex;
	margin: 0 auto;
	justify-content: center;
	flex-direction: column;
	width: 400px;
}

.submit-btn {
	border-radius: 50px;
	width: 175px;
	margin: 0 auto;
	background-color: #ff3e00;
	color: white;
	cursor: pointer;
}

.submit-btn:hover {
	border: 1px solid red
}
</style>