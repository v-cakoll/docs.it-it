---
title: /delaysign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c42e351808281d90eafdb6e61a3f1736ef15c9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="delaysign"></a>/delaysign
Specifica se l'assembly avrà firma completa o parziale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Parametro facoltativo. Usare `/delaysign-` se si desidera che l'assembly abbia firma completa. Utilizzare `/delaysign+` se si desidera inserire la chiave pubblica nell'assembly e riservare spazio per l'hash con segno. Il valore predefinito è `/delaysign-`.  
  
## <a name="remarks"></a>Note  
 Il `/delaysign` opzione ha effetto solo se utilizzata con [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata. La firma digitale risultante viene archiviata nel file contenente il manifesto. Quando un assembly è impostata la firma ritardata, il compilatore non calcola e archivia la firma ma riserva lo spazio nel file in modo che la firma possa essere aggiunta successivamente.  
  
 Ad esempio, tramite `/delaysign+`, uno sviluppatore di un'organizzazione può distribuire versioni di prova senza segno di un assembly che i tester possono registrare con la global assembly cache e utilizzare. Al termine di lavoro per l'assembly, la persona responsabile per la chiave privata dell'organizzazione può firmare completamente l'assembly. In questo contesto protegge la chiave privata dell'organizzazione dalla divulgazione, consentendo a tutti gli sviluppatori di utilizzare gli assembly.  
  
 Vedere [creazione e uso degli assembly](https://msdn.microsoft.com/library/xwb8f617) per ulteriori informazioni su come firmare un assembly.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Per impostare /delaysign in Visual Studio ambiente di sviluppo integrato.  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Fare clic sulla scheda **Firma**.  
  
3.  Impostare il valore di **solo firma ritardata** casella.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
