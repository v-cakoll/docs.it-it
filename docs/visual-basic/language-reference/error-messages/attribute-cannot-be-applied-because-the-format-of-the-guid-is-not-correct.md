---
title: "&#39; &lt;attributo&gt;&#39; non può essere applicato perché il formato del GUID &#39;&lt; numero&gt;&#39; non è corretto"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords: BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ead07d12064dbe18a1e23d4d1343b1efba1b533
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>&#39; &lt;attributo&gt;&#39; non può essere applicato perché il formato del GUID &#39;&lt; numero&gt;&#39; non è corretto
Oggetto `COMClassAttribute` blocco di attributi specifica un identificatore univoco globale (GUID) che non è conforme al formato appropriato per un GUID. `COMClassAttribute`utilizza i GUID per identificare in modo univoco la classe, l'interfaccia e l'evento di creazione.  
  
 Un GUID è composto da 16 byte (otto byte numerici seguiti da otto byte binari). È stato generato da utilità Microsoft quali uuidgen.exe ed è sicuramente univoco nello spazio e tempo.  
  
 **ID errore:** BC32500  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare il GUID corretto o il GUID necessarie per identificare l'oggetto COM.  
  
2.  Verificare che le stringhe GUID presentate al blocco di attributi `COMClassAttribute` siano copiate correttamente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Guid>  
[Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)

