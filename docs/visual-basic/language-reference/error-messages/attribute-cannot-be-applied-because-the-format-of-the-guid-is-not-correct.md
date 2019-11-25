---
title: Impossibile applicare '<attribute>' perché il formato del GUID '<number>' non è corretto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: f7b6e42480075666ce9f7e8fc6966bd4bb6b888a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977320"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>non è possibile applicare '\<attribute >' perché il formato del GUID '\<number >' non è corretto

Un blocco di attributi `COMClassAttribute` specifica un identificatore univoco globale (GUID) che non è conforme al formato appropriato per un GUID. `COMClassAttribute` usa i GUID per identificare in modo univoco la classe, l'interfaccia e l'evento di creazione.  
  
 Un GUID è composto da 16 byte (otto byte numerici seguiti da otto byte binari). Viene generato da utilità Microsoft, ad esempio uuidgen. exe, ed è sicuramente univoco nello spazio e nel tempo.  
  
 **ID errore:** BC32500  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Determinare il GUID o i GUID corretti necessari per identificare l'oggetto COM.  
  
2. Verificare che le stringhe GUID presentate al blocco di attributi `COMClassAttribute` siano copiate correttamente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Guid>
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
