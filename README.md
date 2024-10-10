# Lecture_linux_docker_selenoid_CICD
Lecture for AQA linux, docker, selenoid, CI/CD with info, lessons and links

### Titles
<details><summary>Titles:</summary>
	
	- linux commands
	- docker
	- Jenkins & TeamCity
	- Let's code
 
</details>
	
### SSH
<details><summary>SSH commands:</summary>
	
	ssh-keygen
	ssh -i ~/.ssh/test.pub <login>@<public ip>
 
 </details>
	
## Linux commands
<details><summary>Linux commands:</summary>
	
	ls -la - посмотреть содержимое каталога
	cd - сменить категорию
	mkdir - создать каталог
	touch - создать файл
	cp - скопировать
	mv - перемещение файла каталога
	--help, -h - флаг для отображения документации
	man - команда для отображения документации
	sudo - выполнение команды под привилигированным пользователем
	chmod - изменить права доступа
	chown - смена пользователя
	top - команда для просмотра использования ресурсов
	grep - поиск по передаваемым данным
 
 </details>
	
	Более подробней можно ознакомиться тут: https://habr.com/ru/articles/655275/
	
### Docker commands
<details><summary>Docker commands:</summary>
	
	docker ps - посмотреть запущенные контейнеры
	docker pa -a - посмотреть запущенные и осттановленные контейнеры
	docker stop - остановить контейнер
	docker rm - удалить контейнер
	docker rmi - удалить образ
	docker pull - скачать образ из удаленного репозитория
	docker push - загрузить образ в удаленный репозиторий
 
 </details>
	
	Более подробней с командами можно ознакомиться тут: https://docs.docker.com/reference/cli/docker/
	
### Docker install
<details><summary>Docker install commands:</summary>
	
	sudo apt install docker.io -y
	sudo usermod -aG docker $USER
 
  </details>
	
### Selenoid run
<details><summary>Selenoid run commands:</summary>
	
	docker run -d                                   \
	--name selenoid                                 \
	-p 4444:4444                                    \
	-v /var/run/docker.sock:/var/run/docker.sock    \
	-v /your/directory/config/:/etc/selenoid/:ro    \
	aerokube/selenoid:latest-release
	
	docker pull selenoid/chrome:120.0
 
  </details>

	Более подробней с командами можно ознакомиться тут: https://aerokube.com/selenoid/latest/

 <details><summary>Selenoid command line:</summary>
	
	./cm_linux_amd64 selenoid start -c /home/admin/config/
 
  </details>

  	Более подробней с командами можно ознакомиться тут: https://aerokube.com/cm/latest/

	
	
### Jenkins install
<details><summary>Jenkins install commands:</summary>
	
	sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
	  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
	echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
	  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
	  /etc/apt/sources.list.d/jenkins.list > /dev/null
	sudo apt-get update
	sudo apt-get install jenkins
	sudo apt install maven -y
	sudo apt install openjdk-11-jre-headless -y
	sudo systemctl enable jenkins
	sudo systemctl status jenkins
	cat /var/lib/jenkins/secrets/initialAdminPassword
 
</details>
	
### Team city install
	https://www.jetbrains.com/help/teamcity/install-teamcity-server-on-linux-or-macos.html#Example%3A+Installation+using+Ubuntu+Linux
	
### Allure guide
	https://allurereport.org/docs/
	
	
### Home task:
 <details><summary>Easy peasy lemon squeezy:</summary>
	 
		Docker:
			- Установить docker*;
			- Запустить контейнер с selenoid;
			- Запустить свои тесты в селенойде.
			Для проверки выполнения прислать скриншоты:
				- команды docker ps или UI с поднятым контейнером selenoid;
				- скриншот из браузера с выводом статуса selenoid с запущенной сессией.
		Jenkins:
			- Создать билд, который запускает (группу | профиль | папку) с вашими тестами из вашего публичного репозитория в определенное время;
			- Настроить создание Allure отчета в вашем билде.
			Для проверки выполнения прислать ссылку на билд.
			
		* - для работы docker на Windows потребуется WSL (подсистема Windows для Linux), которой нет в старых версиях Windows. В таком случае можно установить один из сервесов для виртуализации и запустить виртуальную машину, например под Linux.
  
</details>

 <details><summary>Job hard go pro (необязательное задание для скилловичков, можно выполнить только часть):</summary>
	 
		Docker:
			- выполнить задание из раздела "Easy peasy lemon squeezy" на виртуальной машине или сервере linux;
			- добавить поддержку нескольких версий браузеров;
			- добавить настройки selenoid тайм аутов для контейнеров с браузерами и ограничить количество сессий 16;
			- запустить контейнер с selenoid-ui (https://aerokube.com/selenoid-ui/latest/).
			Для проверки выполнения прислать скриншоты:
				- команды docker ps или UI с поднятым контейнером selenoid и selenoid-ui;
				- скриншот из браузера с выводом статуса selenoid и selenoid-ui с запущенной сессией.
		(Jenkins | TeamCity):
			- установить (Jenkins | TeamCity) на виртуальной машине или сервере linux;
			- выполнить задание из раздела "Easy peasy lemon squeezy" на виртуальной машине или сервере linux.
			Для проверки выполнения прислать ссылку на билд и логин с паролем от учетки, чтобы проверить, или скриншоты если делали через виртуальную машину локально.
   
</details>

		
### Meta server info:
 <details><summary>Meta server info:</summary>
	 
	- Selnoid:
		url: http://89.169.147.50:4444/
	- Jenkins:
		url: http://89.169.147.50:8080
		login: aqa
  		pass: in work chat
	- Teamcity:
		url: n/a
		login: n/a
	- Versions:
		java: openjdk 17.0.12
		maven: 3.8.7
		gradle: 4.4.1
		docker: 24.0.7
  
</details>


