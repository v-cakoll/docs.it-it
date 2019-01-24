---
title: '&#39;&lt;attributo&gt; &#39; non può essere applicato perché il formato del GUID &#39; &lt;numero&gt; &#39; non è corretto'
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 85b8c9dcccbb307d8a744e33a5f1d4b1775fda04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623664"
---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>&#39;&lt;attributo&gt; &#39; non può essere applicato perché il formato del GUID &#39; &lt;numero&gt; &#39; non è corretto
Oggetto `COMClassAttribute` blocco di attributi specifica un identificatore univoco globale (GUID) che non corrisponde al formato corretto per un GUID. `COMClassAttribute` Usa i GUID per identificare in modo univoco la classe, l'interfaccia e l'evento di creazione.  
  
 Un GUID è composto da 16 byte (otto byte numerici seguiti da otto byte binari). È generato da utilità Microsoft quali uuidgen.exe ed è sicuramente univoco nello spazio e tempo.  
  
 **ID errore:** BC32500  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare il GUID corretto o il GUID necessarie per identificare l'oggetto COM.  
  
2.  Verificare che le stringhe GUID presentate al blocco di attributi `COMClassAttribute` siano copiate correttamente.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Guid>
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)

