---
title: La proprietà '<propertyname>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 21a1c4dbab6e26cd1cb848e270bbda9a544c2a67
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400422"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>La proprietà '\<propertyname>' non restituisce un valore in tutti i percorsi del codice
La proprietà' \<propertyname> ' non restituisce un valore per tutti i percorsi del codice. In fase di esecuzione, quando viene usato il risultato, potrebbe verificarsi un'eccezione dovuta a un riferimento Null.  
  
 Una routine di proprietà `Get` ha almeno un possibile percorso nel codice che non restituisce un valore.  
  
 È possibile restituire un valore da una routine di proprietà `Get` in uno dei modi seguenti:  
  
- Assegnare il valore al nome della proprietà, quindi eseguire un' `Exit Property` istruzione.  
  
- Assegnare il valore al nome della proprietà, quindi eseguire l' `End Get` istruzione.  
  
- Includere il valore in un' [istruzione return](../statements/return-statement.md).  
  
 Se il controllo passa a `Exit Property` o `End Get` e non è stato assegnato alcun valore al nome della proprietà, la `Get` stored procedure restituisce il valore predefinito del tipo di dati della proprietà. Per ulteriori informazioni, vedere "Behavior" nell' [istruzione Function](../statements/function-statement.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42107  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.  
  
     È più facile garantire che ogni ritorno dalla procedura restituisca un valore se si usa sempre l' `Return` istruzione. In tal caso, l'ultima istruzione prima `End Get` deve essere un' `Return` istruzione.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Istruzione Get](../statements/get-statement.md)
