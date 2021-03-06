## Git
### gitflow workflow
> 중앙 원격 저장소에서 master와 develop, 두 개의 메인 브랜치를 이용.
- master branch : 릴리스 이력을 관리하기 위해 사용. 배포 가능한 상태를 관리.
- develop branch : 기능 개발을 위한 브랜치들을 병합하기 위해 사용. (기능 추가, 버그 수정 후 'master' 브랜치로 merge

``` $ git clone [remote repository URL] ```
> 

### git Branch 종류
1. Master Branch
	-> 제품으로 출시될 수 있는 브랜치
	배포 이력을 관리하기 위해 사용. 즉, 배포 가능한 상태만을 관리
2. Develop Branch
	-> 다음 출시 버전을 개발하는 브랜치
    기능 개발을 위한 브랜치들을 병합하기 위해 사용. 
	즉, 모든 기능이 추가되고 버그가 수정되어 배포 가능한 안정적인 상태라면 develop 브랜치를 'master' 브랜치에 병합한다.
	평소에는 이 브랜치를 기반으로 개발을 진행
3. Feature Branch
	-> 기능을 개발하는 브랜치
	새로운 기능 개발 및 버그 수정이 필요할 때마다 'develop' 브랜치로부터 분기한다.
	feature 브랜치에서의 작업은 기본적으로 공유할 필요가 없기 때문에, 자신의 로컬 저장소에서 관리
	개발이 완료되면 'develop' 브랜치로 병합하여 다른 사람들과 공유
	> 1. 'develop' 브랜치에서 새로운 기능 개발 위한 'feature' 브랜치 분기
	> 2. 새로운 기능에 대한 작업 수행
	> 3. 작업이 끝나면 'develop' 브랜치로 병합
	> 4. 더이상 필요하지 않은 feature 브랜치 삭제
	> 5. 새로운 기능에 대한 'feature' 브랜치를 중앙 원격 저장소에 올림.
4. Release Branch
	-> 이번 출시 버전을 준비하는 브랜치
	배포를 위한 전용 브랜치를 사용해서 해당 배포를 준비하는 동안 다른 팀은 다음 배포를 위한 기능 개발을 계속 할 수 있다.
	> 1. 'develop' 브랜치에서 배포할 수 있는 수준의 기능이 모이면 또는 정해진 배포 일정이 되면, release 브랜치를 분기한다.
	> 2. 'release' 브랜치에서 배포 가능한 상태가 되면, 'master' 브랜치에 병합한다, 배포를 준비하는 동안 release 브랜치가 변경되었을 수 있으므로 배포 완료 후 'develop' 브랜치에도 병합한다.
	>
	> * 배포를 준비하는 동안 다음 배포를 위한 작업은 'develop' 브랜치에서 계속 진행해 나간다.
5. Hotfix Branch
	-> 출시 버전에서 발생한 버그를 수정하는 브랜치
	배포한 버전에 긴급하게 수정을 해야 할 필요가 있을 경우, 'master' 브랜치에서 분기하는 브랜치이다. 빠르게 수정하고 배포하기 위해 바로 배포 가능한 'master' 브랜치에서 직접 브랜치를 만들어 수정한 후 'master' 브랜치에 병합하여 배포
	> 1. 배포한 버전에 긴급한 수정이 필요한 경우 'master' 브랜치에서 'hotfix' 브랜치를 분기
	> 2. 문제가 되는 부분을 수정
	> 3. 다시 'master' 브랜치에 병합하여 배포 및 새로운 버전 이름으로 태그를 매김.
	> 4. 'hotfix' 브랜치에서 변경 사항 'develop' 브랜치에도 병합.