# Git/GitHub 빠른 시작

## 1) 최초 설정(한 번만)
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## 2) 새 레포 만들기
GitHub → New repository → 이름: `study-log` (Public/Private 선택)

## 3) 클론
```bash
git clone https://github.com/<your-id>/study-log.git
cd study-log
```

## 4) 이 스타터 파일 복사 → 커밋/푸시
```bash
git add .
git commit -m "chore: bootstrap study-log starter"
git push origin main
```

Tip: JetBrains(GoLand/PhpStorm)에서는 **VCS → Get from Version Control** 사용.
