---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775629"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Specifica il nome dell'assembly di cui fa parte il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`assembly_name`|Nome dell'assembly di cui questo modulo farà parte.|  
  
## <a name="remarks"></a>Osservazioni  
 Il compilatore elabora l' `-moduleassemblyname` opzione solo se è `-target:module` stata specificata l'opzione. In questo modo il compilatore crea un modulo. Il modulo creato dal compilatore è valido solo per l'assembly specificato con l' `-moduleassemblyname` opzione. Se si inserisce il modulo in un assembly diverso, si verificheranno errori di run-time.  
  
 L' `-moduleassemblyname` opzione è necessaria solo quando sono soddisfatte le condizioni seguenti:  
  
- Un tipo di dati nel modulo deve accedere a un `Friend` tipo in un assembly a cui si fa riferimento.  
  
- L'assembly a cui si fa riferimento ha concesso l'accesso dell'assembly Friend all'assembly in cui verrà compilato il modulo.  
  
 Per ulteriori informazioni sulla creazione di un modulo, vedere [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Per ulteriori informazioni sugli assembly Friend, vedere [assembly Friend](../../../standard/assembly/friend.md).  
  
> [!NOTE]
> L' `-moduleassemblyname` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si compila da un prompt dei comandi.  
  
## <a name="see-also"></a>Vedi anche

- [Procedura: compilare un assembly su più file](../../../framework/app-domains/build-multifile-assembly.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Assembly Friend](../../../standard/assembly/friend.md)
