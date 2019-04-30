---
title: La proprietà '<propertyname>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: a535a6b951dc9872109527f78d7de5f3fcdd3292
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971644"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>Proprietà '\<NomeProprietà >' non restituisce un valore per tutti i percorsi del codice
Proprietà '\<NomeProprietà >' non restituisce un valore per tutti i percorsi del codice. In fase di esecuzione, quando viene usato il risultato, potrebbe verificarsi un'eccezione dovuta a un riferimento Null.  
  
 Una proprietà `Get` procedure dispone di almeno un possibile percorso all'interno del codice che non restituisce un valore.  
  
 È possibile restituire un valore da una proprietà `Get` procedure in uno dei modi seguenti:  
  
- Assegnare il valore per il nome della proprietà, quindi eseguire un `Exit Property` istruzione.  
  
- Assegnare il valore per il nome della proprietà, quindi eseguire il `End Get` istruzione.  
  
- Includere il valore in una [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Se il controllo passa al `Exit Property` oppure `End Get` e non è stato assegnato alcun valore per il nome della proprietà di `Get` procedure restituisce il valore predefinito della proprietà tipo di dati. Per altre informazioni, vedere "Comportamento di" nella [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42107  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Controllare la logica del flusso di controllo e assicurarsi che si assegna un valore prima di ogni istruzione che provoca un valore restituito.  
  
     È più semplice garantire che ogni restituito dalla routine restituisce un valore se si usano sempre il `Return` istruzione. Se si esegue questa operazione, l'ultima istruzione che precede `End Get` deve essere un `Return` istruzione.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)
