---
title: Commenti nel codice
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: 189810393db42c54cb8a0f97b22b3d1514d9a7c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346165"
---
# <a name="comments-in-code-visual-basic"></a>Commenti nel codice (Visual Basic)
Negli esempi di codice viene spesso utilizzato il simbolo di commento (`'`). Questo simbolo indica al compilatore Visual Basic di ignorare il testo che lo segue o il *Commento*. I commenti sono brevi annotazioni descrittive che vengono aggiunte al codice per agevolarne la lettura.  
  
 È buona norma di programmazione iniziare tutte le routine con un breve commento che ne descriva le caratteristiche funzionali, ovvero le operazioni che vengono compiute. Ciò può rivelarsi a proprio vantaggio e di chi esaminerà il codice. È opportuno separare le informazioni dettagliate relative alle modalità di implementazione dai commenti che descrivono le caratteristiche funzionali. Quando si includono informazioni dettagliate sulle modalità di implementazione, è importante che queste vengano aggiornate contestualmente all'aggiornamento della funzione.  
  
 I commenti possono seguire un'istruzione sulla stessa riga oppure occupare una riga intera. Nell'esempio di codice seguente vengono illustrate entrambe le opzioni.  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 Se il commento richiede più di una riga, utilizzare il simbolo di commento su ogni riga, così come viene illustrato nell'esempio seguente:  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a>Indicazioni sui commenti  
 Nella tabella riportata di seguito vengono fornite indicazioni generali sui tipi di commenti che possono precedere una sezione del codice. Si tratta di suggerimenti; Visual Basic non impone regole per l'aggiunta di commenti. Scrivere il testo che si ritiene più adatto alle proprie esigenze e a quelle di chi leggerà il codice.  
  
|||  
|---|---|  
|Tipo di commento|Descrizione del commento|  
|Scopo|Descrive le operazioni eseguite dalla routine, non la modalità di esecuzione|  
|Presupposti|Elenca tutte le variabili esterne, i controlli, i file aperti o gli altri elementi a cui accede la routine|  
|Effetti|Elenca tutte le variabili esterne, i controlli o i file interessati, nonché l'effetto su di essi (solo se non è ovvio)|  
|Input|Specifica lo scopo dell'argomento|  
|Valore restituito|Spiega i valori restituiti dalla routine|  
  
 È importante tenere presente i seguenti punti:  
  
- Le dichiarazioni di variabili importanti devono essere precedute da un commento in cui viene descritto l'utilizzo della variabile dichiarata.  
  
- I nomi di variabili, controlli e routine devono essere descrittivi in modo da rendere necessaria l'aggiunta di commenti solo per la descrizione di implementazioni complesse.  
  
- Non è possibile inserire sulla stessa riga una sequenza di continuazione di riga seguita da un commento.  
  
 È possibile aggiungere o rimuovere i simboli di commento per un blocco di codice selezionando una o più righe di codice e scegliendo il **Commento** (![pulsante Visual Basic commento in Visual studio.](./media/comments-in-code/visual-basic-comment-button.gif)) e rimuovere il **Commento** (![il pulsante Visual Basic Rimuovi commento nei pulsanti di Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) sulla barra degli strumenti di **modifica** .  
  
> [!NOTE]
> Per aggiungere commenti al codice è possibile anche inserire la parola chiave `REM` prima del testo. Tuttavia, il simbolo `'` e i pulsanti **commento**/Rimuovi **Commento** sono più semplici da utilizzare e richiedono meno spazio e memoria.  
  
## <a name="see-also"></a>Vedere anche

- [Istinti di base-documentazione del codice con commenti XML](https://docs.microsoft.com/archive/msdn-magazine/2009/may/documenting-your-code-with-xml-comments)
- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Istruzione REM](../../../visual-basic/language-reference/statements/rem-statement.md)
