---
title: -main (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 6c842abc1423e7ee0d98b71392e02410c6cf9172
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602731"
---
# <a name="-main-c-compiler-options"></a>-main (opzioni del compilatore C#)
Questa opzione specifica la classe che contiene il punto di ingresso al programma, quando più classi contengono un metodo **Main**.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a>Argomenti  
 `class`  
 Il tipo contenente il metodo **Main**.  
 Il nome della classe specificato deve essere completo. Deve includere lo spazio dei nomi completo che contiene la classe, seguito dal nome della classe. Ad esempio, quando il metodo `Main` è all'interno della classe `Program` nello spazio dei nomi `MyApplication.Core`, l'opzione del compilatore deve essere `-main:MyApplication.Core.Program`.
  
## <a name="remarks"></a>Osservazioni  
 Se la compilazione include più tipi con un metodo [Main](../../programming-guide/main-and-command-args/index.md), è possibile specificare il tipo che contiene il metodo **Main** che si vuole usare come punto di ingresso nel programma.  
  
 Usare questa opzione solo durante la compilazione di un file con estensione exe.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3. Modificare la proprietà **Oggetto di avvio**.  
  
     Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `t2.cs` e `t3.cs` specificando che il metodo **Main** si trova in `Test2`:  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
