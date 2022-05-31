// เปิด TextEdit
// เมนูรูปแบบ
// เลือกทำข้อความเข้ารหัสแอสกี (RTF)
// เริ่มต้น ประกาศ pipeline แล้วตามด้วย { ... }
pipeline {
	// ถัดมา กำหนด agent และ stages ต่างๆ
	// agent เป็นคำสั่งที่เอาไว้บอก Jenkins ว่าจะให้ใช้ executor ตัวไหนมา run คำสั่งใน stages เช่น
	// - none คือ ไม่ใช้ executor ใดๆ สำหรับ stages ทั้งหมด (ต้องไปกำหนด executor แยกสำหรับแต่ stage เอง)
	// - any คือ ใช้ executor ใดๆ ก็ได้
	// - docker คือ ใช้ docker executor มา run stages ทั้งห
	agent any
	// stage เปรียบเสมือนกับ Flow การทำงาน ว่าจะให้ทำอะไรบ้างใน Pipeline นี้ เช่น
	// - การ Build Code Frontend (Angular, VueJS, React, ect)
	// - การ Test Code Frontend
	// - การ Build Code Backend
	// - การ Test Code Backend
	// - การ Build Docker Image
	// - การ Push Docker Image ไปยัง Registry
	// - การ ออก Report
	// - การ Deploy
	stages{
		// ถัดมา ในแต่ละ stage ให้กำหนด steps การทำงาน เพื่อบอก Jenkins ว่าจะให้ทำอะไร ยังไงบ้างใน stage นี้
		stage('Init'){
			// สามารถใส่ step การทำงานภายใน steps { ... } ได้หลาย steps เช่น
			// - echo เป็นคำสั่งที่ใช้ในการ print (log) ข้อความต่าง ๆ ออกมาดู
			// - sh เป็นคำสั่งที่ใช้ในการ run Linux Command เช่น
			// -- sh 'node --version'
			// -- sh 'cd frontend && yarn build'
			// -- sh 'chmod 744 deploy.sh'
			steps{
				echo 'Init'
				echo '******************************'
				// กำหนดให้ Pipeline ใช้งานจากตัวแปร env หรือ Environment ต่างๆของระบบได้ โดยการใช้ ${env.XXXXX}
				// การใช้ตัวแปร env ต้องทำภายใน String (") เท่านั้น เพราะถ้าใช้ (') ตัวแปร env จะไม่ทำงาน
				echo "build number : ${env.BUILD_NUMBER}"
			}
		}
		stage('Yarn Install'){
			steps{
				echo 'Yarn Install'
				echo '******************************'
			}
		}
		stage('Yarn Build'){
			steps{
				echo 'Yarn Build'
				echo '******************************'
			}
		}
		stage('Mvn Install'){
		    steps{
				echo 'Mvn Install'
				echo '******************************'
			}
		}
		stage('Mvn Test'){	
		    steps{
				echo 'Mvn Test'
				echo '******************************'
			}
		}
		stage('Docker Build'){
		    steps{
				echo 'Docker Build'
				echo '******************************'
			}
		}
		stage('Docker Push'){
		    steps{
				echo 'Docker Push'
				echo '******************************'
			}
		}
		stage('Deploy'){
			steps{
				echo 'Deploy'
				echo '******************************'
			}
		}
	}
}
