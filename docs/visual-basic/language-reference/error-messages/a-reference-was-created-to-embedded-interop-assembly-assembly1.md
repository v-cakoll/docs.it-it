---
title: "È stato creato un riferimento all'assembly di interoperabilità incorporato &#39; &lt;assembly1&gt;&#39; a causa di un riferimento indiretto all'assembly dall'assembly &#39;&lt; Assembly2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bc2fbb044fc839aa24abf3dc1ea864457efb0653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a>È stato creato un riferimento all'assembly di interoperabilità incorporato &#39; &lt;assembly1&gt;&#39; a causa di un riferimento indiretto all'assembly dall'assembly &#39;&lt; Assembly2&gt;&#39;
È stato creato un riferimento all'assembly di interoperabilità incorporato '\<assembly1>' a causa di un riferimento indiretto a tale assembly creato dall'assembly '\<assembly2>'. Provare a modificare la proprietà 'Incorpora tipi di interoperabilità' in un assembly.  
  
 È stato aggiunto un riferimento a un assembly (assembly1) con la proprietà `Embed Interop Types` impostata su `True`. Si dà così istruzione al compilatore di incorporare le informazioni sui tipi di interoperabilità da tale assembly. Il compilatore non può tuttavia incorporare le informazioni sui tipi di interoperabilità da tale assembly perché anche un altro assembly a cui si fa riferimento (assembly2) fa riferimento a tale assembly (assembly1) e ha la proprietà `Embed Interop Types` impostata su `False`.  
  
> [!NOTE]
>  L'impostazione della proprietà `Embed Interop Types` per un riferimento a un assembly su `True` equivale a fare riferimento all'assembly usando l'opzione del compilatore della riga di comando `/link`.  
  
 **ID errore:** BC40059  
  
### <a name="to-address-this-warning"></a>Per risolvere questo avviso  
  
-   Per incorporare le informazioni sui tipi di interoperabilità per entrambi gli assembly, impostare la proprietà `Embed Interop Types` per tutti i riferimenti a assembly1 su `True`.  
  
-   Per rimuovere l'avviso, è possibile impostare la proprietà `Embed Interop Types` di assembly1 su `False`. In questo caso, vengono fornite informazioni di tipo di interoperabilità dall'assembly di interoperabilità primario (PIA).  
  
## <a name="see-also"></a>Vedere anche  
 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)  
 [Programmazione con assembly di interoperabilità primari](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)
