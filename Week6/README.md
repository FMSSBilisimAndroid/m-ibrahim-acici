1.Döngü kilitlenmeye sebep olacak mı ? 
2.Kilitlenmeye sebep olmadan  aşağıdaki blok çalışır mı ?

CoroutineScope(Dispatchers.IO).launch {
            val answer = doNetworkCall()
            withContext(Dispatchers.Main){
                Log.v("PATIKA",answer)
            }
        } 

1.Evet,döngü kilitlenir.
Döngü bitene kadar main thread kilitlendi.
2.Hayır,çalışmaz.
Oluşturduğumuz sonsuz döngü ana thread'de çalıştığı için, döngüyü bitirmeden blok çalışmaz.
