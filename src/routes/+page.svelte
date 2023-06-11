<script>

	let questions = [
		{
			"question":"O’rdaklar suv ichishga qator bo’lib ketayotgan edi. O’rdaklardan biri oldinga qarab, 17 ta boshni ko’rdi. Ortiga qarasa — 42 ta panja kelayotgan ekan. Jami nechta o’rdak suv ichishga ketmoqda?",
			"options": [
				" 37 ta ",
				" 38 ta ",
				" 39 ta ",
				" 40 ta "
			],
			"correctIndex":1
		},
		{
			"question":"Hamma narsani ko’rayotganda uni ko’rmaysiz, Hech narsani ko’rmaganda esa uni ko’ra olasiz, U nima?",
			"options": [
				" Quyosh ",
				" Qorong'ulik ",
				" Havo ",
				" Yurak "
			],
			"correctIndex":1
		},
		{
			"question":"Professor do’stlarini o’zining maxsus salati bilan mehmon qilishni niyat qildi. Buning uchun unga: 3 ta bulg’or qalampiri va huddi shuncha pomidor, pomidorlardan ko’ra kamroq, ammo piyozdan ko’proq bodring kerak bo’ladi. Professor jami bo’lib necha dona turli xil sabzavotlar ishlatadi?",
			"options": [
				" 8 ta ",
				" 9 ta ",
				" 10 ta ",
				" 5 ta "
			],
			"correctIndex":1
		},
		{
			"question":"Nimani 10 daqiqadan ortiq ushlab turishning iloji yo’q, garchi u o’ta yengil bo’lsa ham?",
			"options": [
				" Issiq Cofeni ",
				" Muzni ",
				" Nafasni",
				" Sichqonni "
			],
			"correctIndex":2
		},
		{
			"question":"Ular qanchalik ko’p bo’lsa, vazni shunchalik kamayib ketaveradi?",
			"options": [
				" Chuqurlar ",
				" Go'vaklar ",
				" Arilar ",
				" Quyonlar "
			],
			"correctIndex":1
		},
		{
			"question":"Bu shaharga mo'gullar asos solishgan. Uning ma'nosi (Saroy) degani, bu qaysi shahar ekanligini emas, u qaysi viloyat poytaxti ekanligini toping?",
			"options": [
				" Xorazm ",
				" Buxoro ",
				" Qashqadaryo ",
				" Surxondaryo "
			],
			"correctIndex":2
		},
		{
			"question":"Ukraina, Xitoy, Turkiya, Kanada kabi davlatlarda u 2 ta, O’zbekistоn, Rоssiya, Fransiya, Italiya kabi davlatlarda – 3 ta, Efiоpiya, Surinam, Quvayt, Suriyada – 4 ta. Savоl: Lixtenshteyn va Liviyada u nechta?",
			"options": [
				" 4 ta ",
				" 3 ta ",
				" 3 ta ",
				" 1 ta "
			],
			"correctIndex":3
		},
		{
			"question":"Tseylonda har bir oilaniki alohida o’z hovlisida joylashgan, bizning yerlarda esa hammaniki umumiy. Savol: nima haqida gap ketmoqda?",
			"options": [
				" Uy ",
				" Mashina ",
				" Qabriston ",
				" Mousqe "
			],
			"correctIndex":2
		},
		{
			"question":"VII-VIII asrlarda Eronda topilgan tarixiy hujjatda shunday majburiyatlar yozilgan edi: “Xudo nomi bilan qasam ichaman, uni sotmayman, qarz hisobiga qullikka ham, boshqalar himoyasiga ham bermayman” Savol: ushbu hujjatda qanday majburiyat zikr etilgan?",
			"options": [
				" Erning xotin oldidagi majburiyati ",
				" Ilohiy kitobning majburiyati ",
				" Otaning qizi oldidagi majburiyati ",
				" Bola asrab olayotgan otaning majburiyati "
			],
			"correctIndex":0
		},
		{
			"question":"Tizza bo’g’imlari 4 ta bo’lgan yagona sutemizuvchi hayvon qaysi?",
			"options": [
				" Jaguar ",
				" Kenguru ",
				" Fil ",
				" Crocodil "
			],
			"correctIndex":2
		},
		{
			"question":"XIII asrda bu narsaga ehtiyoj sezila boshlagan. XII-XIII asrlarda universitetlarning ko’payganligini bunga sabab sifatida keltirish mumkin. O’sha vaqtgacha uni hech kim bilmagan. Savol: u nima?",
			"options": [
				" Soat ",
				" Ko’zoynak ",
				" Computer ",
				" Bo'r "
			],
			"correctIndex":1
		},
		{
			"question":"Uning o’rnida Sulaymon orollarida odamning bosh suyagi, Santa Krus orollarida qush patlaridan yasalgan 10 metrlik tasma, Tinch okeanidagi ba’zi orollarda 100 yil oldin diametric 4 metrlik bo’lgan toshlar ishlatilgan. Savol: uning o’rnida biz hozir nima ishlatamiz?",
			"options": [
				" Qo'lqop ",
				" Pichoq ",
				" Pul ",
				" Zanjir "
			],
			"correctIndex":2
		},
		{
			"question":"Bozorda ko’rmaysiz, ko’rsangiz ham olmaysiz, olsangiz ham kiymaysiz, kiysangiz ham ko’rmaysiz. U – ?",
			"options": [
				" Shim ",
				" Kepka ",
				" Kafan ",
				" Paypoq "
			],
			"correctIndex":2
		},
	];
	let answers = new Array(questions.length).fill(null);
	let questionPointer = -1;
	function getScore(){
		let score = answers.reduce((acc, val, index)=>{
			if(questions[index].correctIndex == val){
				return acc + 1;
			}
			return acc;
		},0)
		let final = Math.round(score/questions.length*100);
		return (final)+"%";
	}
	function restartQuiz(){
		answers = new Array(questions.length).fill(null);
		questionPointer = 0;
	}
</script>

<style>
.app {
	position: absolute;
	top: 0px;
	left: 0px;
	width: 100vw;
	height: 100vh;
	background: #82a1e7;
}
.app > div {
	width: 100%;
	height: 100%;
}
.app .start-screen,
.app .score-screen {
	display: flex;
	justify-content: center;
	align-items: center;
}
.app .start-screen button,
.app .score-screen button{
	padding: 10px 20px;
	background: #4a77dc;
	color: #eee;
	border: none;
	outline: none;
	border-radius: 20px;
	cursor: pointer;
}
.app .quiz-screen .main{
	padding: 50px;
}
.app .quiz-screen .main .options {
	display: flex;
	justify-content: space-between;
	flex-wrap: wrap;
}
.app .quiz-screen .main .options button {
	width: 45%;
	border-radius: 20px;
	margin: 10px 0px;
}
.app .quiz-screen .main .options button.selected {
	background: #111;
	color: #eee;
}
.app .quiz-screen .footer {
	position: fixed;
	bottom: 0px;
	left: 0px;
	width: 100%;
	height: 50px;
	display: flex;
	justify-content: space-between;
	align-items: center;
	background: #eee;
}
.app .quiz-screen .footer > div {
	margin: 0px 10px;
}
.app .quiz-screen .footer .progress-bar {
	width: 150px;
	height: 10px;
	background: #aaa;
	border-radius: 10px;
	overflow: hidden;
}
.app .quiz-screen .footer .progress-bar div {
	height: 100%;
	background: #4a77dc;
}
.app .score-screen {
	flex-direction: column;
}
.app .score-screen h1 {
	margin-bottom: 10px;
}
</style>

<div class="app">
	{#if questionPointer==-1}

	<div class="start-screen"> 
		<button on:click={()=>{questionPointer=0}}> Start Quiz </button>
	</div>
	
	{:else if !(questionPointer > answers.length-1)}
	<div class="quiz-screen">
		<div class="main">

			<h2>
				{questions[questionPointer].question}
			</h2>
			<div class="options">
				{#each questions[questionPointer].options as opt,i}
				<button class="{answers[questionPointer]==i?'selected':''}" on:click={()=>{answers[questionPointer]=i}}>
					{opt}
				</button>
				{/each}
			</div>
		</div>
		<div class="footer">
			<div class="progress-bar">
				<div style="width:{questionPointer/questions.length * 100}%">
				</div>
			</div>
			<div class="buttons">
				<button disabled={questionPointer==0} on:click={()=>{questionPointer--}}>
				&lt;
				</button>
				<button on:click={()=>{questionPointer++}}>
				&gt;
				</button>
			</div>
		</div>
	</div>
	{:else}
	<div class="score-screen">
		<h1>
			Your Score: {getScore()}
		</h1>
		<button on:click={restartQuiz}>
			Restart Quiz
		</button>
	</div>
	{/if}
</div>