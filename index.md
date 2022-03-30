<h1>Dice Roller</h1>

Dice Roller is a simple app built using [Android.](https://www.android.com/) This project explores the basics of Android, such as creating text, images,
 and interactive buttons. The following is the `MainActivity` class which calls the `rollDice` function on the button click to generate a random number on the die. 
 The `diceImage` ImageView uses the drawable resources included in the project.
 
 ```kotlin
 class MainActivity : AppCompatActivity() {

    private lateinit var diceImage: ImageView
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        val rollButton: Button = findViewById(R.id.roll_button)
        rollButton.setOnClickListener {
            rollDice()
        }
        diceImage = findViewById(R.id.dice_image)
    }

    private fun rollDice() {
        val drawableResource = when (Random().nextInt(6) + 1) {
            1 -> R.drawable.dice_1
            2 -> R.drawable.dice_2
            3 -> R.drawable.dice_3
            4 -> R.drawable.dice_4
            5 -> R.drawable.dice_5
            else -> R.drawable.dice_6
        }
        diceImage.setImageResource(drawableResource)
    }
}
 ```
 The app looks like the following on a real device.
 
 <img align="left" width=396 src="https://github.com/raveerocks/dice-roller/blob/main/screenshot.png" alt="screenshot" />
 
