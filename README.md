Alat koji sam koristio za testiranje je Apache JMeter 5.4.3 zato što on nudi sljedeće prednosti u testiranju:
		● JMeter se može koristiti za testiranje performansi statičkih resursa kao 					što su JavaScript i HTML, kao i dinamičkih, kao što su JSP, Servlets i 	AJAX.
		● JMeter može otkriti maksimalni broj istodobnih korisnika s kojima se
		web-lokacija može nositi
		● JMeter nudi niz grafičkih analiza izvješća o izvedbi.
	
Korištenjem Command Prompt(cmd) sam pokrenio alat Jmeter u kojem sam onda vršio testiranje.

Naredba:
cd C:\Users\Korisnik\apache-jmeter-5.4.3\bin
jmeter


Unutar Test Plana imao sam jednu Thread Groupu.

Unutar upravljačke ploče Thread Group imao sam navedene elemente: 5 HTTP GET Requestova, 1 View Results Tree, 1 Graph Results, 1 Aggregate Report i 1 Aggregate Graph.

Na upravljačkoj ploči grupe Thread, svojstva su mi bila postavljena na sljedeći način:
	● Number of Threads: 10 (Broj korisnika se spaja na ciljnu web stranicu)
	● Ramp-Up Period: 10 (Period pokretanja svih “niti”)
	● Loop Count: 1 (Broj ponavljanja)

Imao sam 5 HTTP GET Requestova (5 testnih slučajeva): ●Wikipedia
						      ●Liquipedia Dota2
						      ●Liquipedia Valorant
						      ●Liquipedia Cs
					   	      ●Liquipedia Rl

Kod HTTP GET Requesta Wikipedia kod opcije Web Server stavio sam Protocol : https, a Server Name or IP:www.wikipedia.org, a kod opcije HTTP Request ostavio sam Path prazan.

Kod HTTP GET Requesta Liquipedia Dota2 kod opcije Web Server stavio sam Protocol : https, a Server Name or IP:liquipedia.net, a kod opcije HTTP Request imao sam Path:/dota2/Main_Page.

Kod HTTP GET Requesta Liquipedia Valorant kod opcije Web Server stavio sam Protocol : https, a Server Name or IP:liquipedia.net, a kod opcije HTTP Request imao sam Path:/valorant/Main_Page.

Kod HTTP GET Requesta Liquipedia Cs kod opcije Web Server stavio sam Protocol : https, a Server Name or IP:liquipedia.net, a kod opcije HTTP Request imao sam Path:/counterstrike/Main_Page.

Kod HTTP GET Requesta Liquipedia Rl kod opcije Web Server stavio sam Protocol : https, a Server Name or IP:liquipedia.net, a kod opcije HTTP Request imao sam Path:/rocketleague/Main_Page.

Pomoću elemenata View Results Tree i Graph Results prikazao sam rezultate ispitivanja u obliku grafikona.

Dok sam za Reporting koristio Aggregate Report i Aggregate Graph.

Kako bi mi se reportovi spremili u cmd sam unjeo naredbu:
jmeter -f -n -t C:\Users\Korisnik\apache-jmeter-5.4.3\bin\LoadTest\Projekt.jmx -l C:\Users\Korisnik\apache-jmeter-5.4.3\bin\LoadTest\loadtest.csv -e -o C:\Users\Korisnik\apache-jmeter-5.4.3\bin\LoadTest\HTMLReport
