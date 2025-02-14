use std::io;
use rand::Rng;

fn main() {
    let secret_number = rand::thread_rng().gen_range(1..101);
    println!("Guess a number between 1 and 100:");

    loop {
        let mut guess = String::new();
        io::stdin().read_line(&mut guess).expect("Failed to read input");

        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,
            Err(_) => {
                println!("Please enter a valid number.");
                continue;
            }
        };

        if guess < secret_number {
            println!("Too low!");
        } else if guess > secret_number {
            println!("Too high!");
        } else {
            println!("You guessed it!");
            break;
        }
    }
}
