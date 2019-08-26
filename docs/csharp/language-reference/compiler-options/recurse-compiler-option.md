---
title: -recurse (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: c82e3019e1a1e3ba45a7000312b54b9d7f64a2db
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606749"
---
# <a name="-recurse-c-compiler-options"></a>-recurse (opzioni del compilatore C#)
L'opzione -recurse consente di compilare i file del codice sorgente in tutte le directory figlio della directory specificata (dir) o della directory del progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argomenti  
 `dir` (facoltativo)  
 La directory in cui si vuole che abbia inizio la ricerca. Se non viene specificata alcuna directory, la ricerca avrà inizio nella directory del progetto.  
  
 `file`  
 I file da cercare. È consentito l'utilizzo di caratteri jolly.  
  
## <a name="remarks"></a>Osservazioni  
 L'opzione **-recurse** consente di compilare file di codice sorgente in tutte le directory figlio della directory specificata (`dir`) o della directory del progetto.  
  
 È possibile usare caratteri jolly in un nome file per compilare tutti i file corrispondenti della directory del progetto senza usare **-recurse**.  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Compila tutti i file C# della directory corrente:  
  
```console  
csc *.cs  
```  
  
 Compila tutti i file C# della directory dir1\dir2 e di eventuali sottodirectory e genera dir2.dll:  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
