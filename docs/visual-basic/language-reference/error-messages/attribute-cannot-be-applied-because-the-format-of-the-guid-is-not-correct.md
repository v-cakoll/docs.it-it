---
title: Impossibile applicare '<attribute>' perché il formato del GUID '<number>' non è corretto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: ab821db45ae834e82aa134b6f20ded14d43709ef
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832268"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>«\<attributo >' non può essere applicato perché il formato del GUID '\<numero >' non è corretto
Oggetto `COMClassAttribute` blocco di attributi specifica un identificatore univoco globale (GUID) che non corrisponde al formato corretto per un GUID. `COMClassAttribute` Usa i GUID per identificare in modo univoco la classe, l'interfaccia e l'evento di creazione.  
  
 Un GUID è composto da 16 byte (otto byte numerici seguiti da otto byte binari). È generato da utilità Microsoft quali uuidgen.exe ed è sicuramente univoco nello spazio e tempo.  
  
 **ID errore:** BC32500  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare il GUID corretto o il GUID necessarie per identificare l'oggetto COM.  
  
2.  Verificare che le stringhe GUID presentate al blocco di attributi `COMClassAttribute` siano copiate correttamente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Guid>
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
