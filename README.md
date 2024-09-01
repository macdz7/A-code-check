export default function Home() {
  const [started, setStarted] = useState(false);
const[currentQuestion, setCurrentQuestion] = useState(0);

  const handleNext = () => {
    if (!started) {
    setStarted(true);
    return; 
  }

  if (currentQuestion < questions.length -1) {
  setCurrentQuestion(currentQuestion + 1); 
  }
  }

  return (
    <div className="flex flex-col flex-1">
    </div>

    <header>
    <ProgressBar value={50} >
    </header>
    </div>
    <main className="flex justify-center flex-1">
      {!started ? <h1 className="text-3xl font-bold">Welcome to StayPolishThinkEnglish👋</h1> : (
      <div>
        <h2 className="text-3xl font-bold">{questions
        [currentQuestion].questionText}</h2>
      <div className ="grid grid-cols-1 gap-6 mt-6">
        {
          questions[currentQuestion].answers.map
          (answer => { 
return (
  <Button key={answer.id} variant= 
  {"secondary"}>{answer.answerText}</Button>
)
          })
        }
      </div>
      </div>
      )}
    </main>
    <footer className="footer pb-9 px-6 relative mb-0">
      <Button onClick={handleNext}>{!started ? 'Start' : 'Next'}</Button>
    </footer>
    </div>
  )
}
