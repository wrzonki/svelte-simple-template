<script>
	let name = 'world';
	let src = 'https://icatcare.org/app/uploads/2018/07/How-to-tell-the-sex-of-a-kitten.png';
	let string = `this string contains some <strong>HTML!!!`;

	let count = 0;
	$: doubled = count * 2;

	function handleClick() {
		count += 1;
	}

$: {
	console.log(`the count is ${count}`);
	console.log(`the double is ${doubled}`);
}

let numbers = [1, 2, 3, 4];

	function addNumber() {
	numbers[numbers.length] = numbers.length + 1;
}
$: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<style>
	p {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
	img {
		width: 200px;
		height: auto;
	}
</style>

<h1>Hello {name}!</h1>
<img src={src} alt={name}/>
<p>This is a paragraph.</p>
<p>{string}</p>
<button on:click={handleClick}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
<p>{count} doubled is {doubled}</p>


<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
	Add a number
</button>
