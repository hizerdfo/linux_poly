---
layout: home
---

# 그룹
리눅스에서 사용자 그룹은 여러 사용자를 논리적으로 묶어서 권한 관리를 용이하게 하는 기능입니다.

## 그룹의 특징
리눅스는 시용자묶음의 그룹 개념이 존재한다. 사용자를 그룹에 포함시키면 그룹의 `권환`을 `공유` 할 수 있다.

### 권환의 공유
리눅스에서는 그룹을 이용하여 파일이나 디렉토리 등의 권한을 공유할 수 있습니다. 그룹에 속한 사용자들은 해당 `그룹으로 설정된 권한을 모두 공유`하게 됩니다.

예를 들어, 파일 A를 소유한 사용자 U1이 파일 A를 그룹 G1에 속한 사용자들과 공유하고 싶다면, U1은 파일 A의 그룹을 G1로 변경해야 합니다. 그룹이 G1로 설정되면, 그룹 G1에 속한 사용자들은 파일 A에 대해 U1과 동일한 권한을 갖게 됩니다. 따라서 그룹을 사용하여 파일에 대한 접근 권한을 관리하면, 관리가 용이해지고 보안성도 높아집니다.

또한, 그룹에 속한 사용자들은 그룹 내에서 자유롭게 파일을 공유하고 협업할 수 있습니다. 이러한 기능은 여러 사용자가 동일한 프로젝트나 작업을 수행하는 경우 매우 유용합니다.

### 하나 이상의 그룹 가입
리눅스 시스템에서 `모든 사용자`는 `하나 이상의 그룹에 소속`되어야 합니다. 이는 보안과 권한 관리 측면에서 중요합니다. 그룹에 속하지 않은 사용자는 파일이나 디렉토리에 대한 권한을 가지지 못하기 때문에, 그룹을 통해 권한을 관리할 수 있습니다.

예를 들어, 파일 A가 그룹 G1으로 설정되어 있다면, G1에 속하지 않은 사용자는 파일 A에 대한 접근 권한이 없습니다. 따라서, 모든 사용자가 하나 이상의 그룹에 소속되어 있어야 파일이나 디렉토리에 대한 권한을 관리할 수 있습니다.

또한, 그룹을 통해 여러 사용자가 동일한 프로젝트나 작업을 수행할 수 있습니다. 그룹에 속한 사용자들은 그룹 내에서 파일을 공유하거나 협업할 수 있습니다. 따라서, 그룹은 파일 접근 권한 관리뿐만 아니라 협업을 위한 기능으로도 사용됩니다.

## 그룹 설정 파일
리눅스는 그룹 정보를 `/etc/group` 파일에 기록 합니다.

* 보조 그룹 사용자는 이 그룹을 주 그룹이 아닌 보조 그룹으로 사용하는 사용자의 목록
* 시용자는 여러 개의 그룹에 포함될 수 있다. 여러 그룹이면 쉼표(,)로 구분

* 각 행은 `그룹이름:비밀번호:그룹id:보조 그룹 사용자`를 의미
![image-20230320171409372](./img/image-20230320171409372.png)

> 현재의 시용자와 그룹을 알아보는 명령어는 `id`, `groups`이다.