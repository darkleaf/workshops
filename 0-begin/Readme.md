# Цели

* Научиться корректно реализовывать задание
* Понять что такое TDD на простом примере
* Понять что такое слоистая архитектура

# Задача

> Представь, что ты работаешь в букмекерской конторе программистом и тебя попросили написать функцию, 
> которая на вход принимает два футбольных счета - тот который загадал клиент когда делал ставку и 
> реальный результат футбольного матча (то как сыграли команды на самом деле). На выходе нужно получить:
> 
> 2 - если клиент полностью угадал счет
> 
> 1 - если клиент угадал какая команда победит или угадал ничью
> 
> 0 - если не угадал ничего

# Где писать код

https://repl.it/C0AP/2

# План

* спросить как бы вы решали эту задачу
* ТЗ => код
* код => ТЗ, код как документация
* абстракция и ревлизация, когда мы говорим, мы не думаем как двигать губами
* пишем код слоями. Т.е. сделали верхний слой, да - нерабочий, потом слой ниже, и так далее.
* TDD

# Посмотреть после

[Ментальное программирование](https://www.youtube.com/watch?v=eEEHWQNuCLQ)

# Тестовый фреймворк

```ruby
AssertionError = Class.new StandardError

def assert(exp, msg = "aserion failed")
	fail AssertionError, msg unless exp
end

def test(name, &block)
	puts name
	block.call
	puts 'Passed'
rescue AssertionError => ex
	puts "Failed: #{ex.message}"
rescue => ex
	puts "Error: #{ex.message}"
ensure
	puts
end

#your code here

test "some test test" do
	assert true
end

test "another test" do
	some_undefined_method
end

test "some another test" do
	assert false, "cool message for this assert"
end
```
