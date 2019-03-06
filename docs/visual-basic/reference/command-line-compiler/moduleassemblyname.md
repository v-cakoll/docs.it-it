---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a16dd616c8a38dea4bd1779e4feea779b3a18e2d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375298"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Specifica il nome dell'assembly di cui fa parte il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`assembly_name`|Il nome dell'assembly che questo modulo farà parte di.|  
  
## <a name="remarks"></a>Note  
 Il compilatore elabora il `-moduleassemblyname` solo se opzione il `-target:module` opzione è stata specificata. Ciò indica al compilatore di creare un modulo. Il modulo è stato creato dal compilatore è valido solo per l'assembly specificato con il `-moduleassemblyname` opzione. Se si inserisce il modulo in un assembly diverso, si verificheranno errori di run-time.  
  
 Il `-moduleassemblyname` opzione è necessaria solo quando vengono soddisfatte le seguenti:  
  
-   Un tipo di dati del modulo deve avere accesso a un `Friend` tipo in un assembly di riferimento.  
  
-   L'assembly di riferimento ha concesso l'accesso assembly friend all'assembly in cui verrà compilato il modulo.  
  
 Per altre informazioni sulla creazione di un modulo, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Per altre informazioni sugli assembly friend, vedere [assembly Friend](../../../standard/assembly/friend-assemblies.md).  
  
> [!NOTE]
>  Il `-moduleassemblyname` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo quando esegue la compilazione da un prompt dei comandi.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Compilare un assembly su più file](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-riferimenti (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Assembly Friend](../../../standard/assembly/friend-assemblies.md)
