---
title: Impossibile applicare '<attribute>' perché il formato del GUID '<number>' non è corretto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: d27c326b6a88271ba4abf0144e71027f6671b17e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330675"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>«\<attributo >' non può essere applicato perché il formato del GUID '\<numero >' non è corretto
Oggetto `COMClassAttribute` blocco di attributi specifica un identificatore univoco globale (GUID) che non corrisponde al formato corretto per un GUID. `COMClassAttribute` Usa i GUID per identificare in modo univoco la classe, l'interfaccia e l'evento di creazione.  
  
 Un GUID è composto da 16 byte (otto byte numerici seguiti da otto byte binari). È generato da utilità Microsoft quali uuidgen.exe ed è sicuramente univoco nello spazio e tempo.  
  
 **ID errore:** BC32500  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Determinare il GUID corretto o il GUID necessarie per identificare l'oggetto COM.  
  
2. Verificare che le stringhe GUID presentate al blocco di attributi `COMClassAttribute` siano copiate correttamente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Guid>
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
