---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 5b26e36346858d95526f5d5ce7d4645bea1dbe05
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005475"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Specifica il nome dell'assembly di cui fa parte il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Nome|Definizione|  
|---|---|  
|`assembly_name`|Nome dell'assembly di cui questo modulo sarà parte.|  
  
## <a name="remarks"></a>Note  
 Il compilatore elabora l'opzione `-moduleassemblyname` solo se è stata specificata l'opzione `-target:module`. In questo modo il compilatore crea un modulo. Il modulo creato dal compilatore è valido solo per l'assembly specificato con l'opzione `-moduleassemblyname`. Se si inserisce il modulo in un assembly diverso, si verificheranno errori di run-time.  
  
 L'opzione `-moduleassemblyname` è necessaria solo quando sono soddisfatte le condizioni seguenti:  
  
- Un tipo di dati nel modulo deve accedere a un tipo `Friend` in un assembly a cui si fa riferimento.  
  
- L'assembly a cui si fa riferimento ha concesso l'accesso dell'assembly Friend all'assembly in cui verrà compilato il modulo.  
  
 Per ulteriori informazioni sulla creazione di un modulo, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Per ulteriori informazioni sugli assembly Friend, vedere [assembly Friend](../../../standard/assembly/friend.md).  
  
> [!NOTE]
> L'opzione `-moduleassemblyname` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si compila da un prompt dei comandi.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Compilare un assembly su più file](../../../framework/app-domains/build-multifile-assembly.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Assembly Friend](../../../standard/assembly/friend.md)
