---
title: La funzione '<procedurename>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: edb2195f4e83c2315aa929936aff8af88ca8556c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374135"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a>La funzione '\<procedurename>' non restituisce un valore in tutti i percorsi del codice
La funzione ' \<procedurename> ' non restituisce un valore in tutti i percorsi del codice. Manca un'istruzione ' Return '?  
  
 Una `Function` routine ha almeno un possibile percorso nel codice che non restituisce un valore.  
  
 È possibile restituire un valore da una `Function` routine in uno dei modi seguenti:  
  
- Includere il valore in un' [istruzione return](../statements/return-statement.md).  
  
- Assegnare il valore al `Function` nome della stored procedure, quindi eseguire un' `Exit Function` istruzione.  
  
- Assegnare il valore al `Function` nome della stored procedure, quindi eseguire l' `End Function` istruzione.  
  
 Se il controllo passa a `Exit Function` o `End Function` e non è stato assegnato alcun valore al nome della stored procedure, la stored procedure restituisce il valore predefinito del tipo di dati restituito. Per ulteriori informazioni, vedere "Behavior" nell' [istruzione Function](../statements/function-statement.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42105  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.  
  
     È più facile garantire che ogni ritorno dalla procedura restituisca un valore se si usa sempre l' `Return` istruzione. In tal caso, l'ultima istruzione prima `End Function` deve essere un' `Return` istruzione.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Function](../../programming-guide/language-features/procedures/function-procedures.md)
- [Istruzione Function](../statements/function-statement.md)
- [Compilazione (pagina), Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
