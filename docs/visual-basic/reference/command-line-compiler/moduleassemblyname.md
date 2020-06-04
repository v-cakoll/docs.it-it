---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 99f2b9d65f3c2a128e026666c5efb384e22643f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403148"
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
  
## <a name="remarks"></a>Commenti  
 Il compilatore elabora l' `-moduleassemblyname` opzione solo se `-target:module` è stata specificata l'opzione. In questo modo il compilatore crea un modulo. Il modulo creato dal compilatore è valido solo per l'assembly specificato con l' `-moduleassemblyname` opzione. Se si inserisce il modulo in un assembly diverso, si verificheranno errori di run-time.  
  
 L' `-moduleassemblyname` opzione è necessaria solo quando sono soddisfatte le condizioni seguenti:  
  
- Un tipo di dati nel modulo deve accedere a un `Friend` tipo in un assembly a cui si fa riferimento.  
  
- L'assembly a cui si fa riferimento ha concesso l'accesso dell'assembly Friend all'assembly in cui verrà compilato il modulo.  
  
 Per ulteriori informazioni sulla creazione di un modulo, vedere [-target (Visual Basic)](target.md). Per ulteriori informazioni sugli assembly Friend, vedere [assembly Friend](../../../standard/assembly/friend.md).  
  
> [!NOTE]
> L' `-moduleassemblyname` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si compila da un prompt dei comandi.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: compilare un assembly su più file](../../../framework/app-domains/build-multifile-assembly.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [-main](main.md)
- [-Reference (Visual Basic)](reference.md)
- [-addmodule](addmodule.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Assembly Friend](../../../standard/assembly/friend.md)
