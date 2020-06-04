---
title: Modificatore 'Custom' non valido negli eventi dichiarati senza tipi delegati espliciti
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 0c5a4188fedf9685afdd1cde4c1de93a0b43b919
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409783"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>Modificatore 'Custom' non valido negli eventi dichiarati senza tipi delegati espliciti
A differenza di un evento non personalizzato, una `Custom Event` dichiarazione richiede una `As` clausola che segue il nome dell'evento che specifica in modo esplicito il tipo di delegato per l'evento.  
  
 Gli eventi non personalizzati possono essere definiti con una `As` clausola e un tipo di delegato esplicito o con un elenco di parametri immediatamente successivo al nome dell'evento.  
  
 **ID errore:** BC31122  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Definire un delegato con lo stesso elenco di parametri dell'evento personalizzato.  
  
     Se, ad esempio, `Custom Event` è stato definito da `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , il delegato corrispondente sarà il seguente.  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. Sostituire l'elenco di parametri dell'evento personalizzato con una `As` clausola che specifica il tipo di delegato.  
  
     Continuando con l'esempio, la `Custom Event` dichiarazione verrebbe riscritta nel modo seguente.  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a>Esempio  
 In questo esempio viene dichiarato un oggetto `Custom Event` e viene specificata la `As` clausola obbligatoria con un tipo delegato.  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Event](../statements/event-statement.md)
- [Istruzione Delegate](../statements/delegate-statement.md)
- [Events](../../programming-guide/language-features/events/index.md)
