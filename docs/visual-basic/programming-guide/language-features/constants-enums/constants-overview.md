---
title: Cenni preliminari sulle costanti (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 2939110de77718baf32e2a0d8f1aa52dba997cf3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907088"
---
# <a name="constants-overview-visual-basic"></a>Cenni preliminari sulle costanti (Visual Basic)
Una costante è un nome significativo che prende il posto di un numero o una stringa che non cambia. Costanti di archiviano i valori, come suggerisce il nome, rimangono invariati durante l'esecuzione di un'applicazione. È notevolmente possibile migliorare la leggibilità del codice e semplificare la manutenzione mediante l'utilizzo delle costanti. Usarli nel codice che contiene valori utilizzati più volte o che dipende da alcuni numeri che sono difficili da ricordare o non hanno alcun significato ovvia.  
  
## <a name="how-to-create-and-use-constants"></a>Come creare e utilizzare le costanti  
 Visual Basic contiene un numero di costanti predefinite, utilizzate principalmente per la stampa e visualizzazione. È anche possibile creare costanti personalizzate con il `Const` istruzione, utilizzando le stesse linee guida si farebbe per la creazione di un nome di variabile. Se `Option Strict` è `On`, è necessario dichiarare in modo esplicito il tipo di costante.  
  
 Ambito di una costante, ovvero il set di tutto il codice che può fare riferimento ad esso senza qualificare il nome, è uguale a quello di una variabile dichiarata nello stesso percorso. Per creare una costante che esiste all'interno dell'ambito di una particolare procedura, dichiararlo all'interno di tale procedura. Per creare una costante che sia disponibile in tutta l'applicazione, dichiarare usando il `Public` parola chiave nella sezione delle dichiarazioni della classe.  
  
> [!NOTE]
>  Sebbene le costanti sono piuttosto simili a variabili, è non è possibile modificarli o assegnare nuovi valori ad essi, come per le variabili.  
  
 Le costanti utilizzate nel codice possono essere definite dal modello a oggetti per i controlli o si lavora con i componenti, oppure possono essere definite dall'utente (vale a dire, ovvero personalizzate).  
  
## <a name="compile-time-and-run-time-constants"></a>Costanti in fase di compilazione e Runtime  
 Una costante in fase di compilazione viene calcolata al momento che il codice viene compilato, mentre è possibile calcolare una costante di runtime solo mentre l'applicazione è in esecuzione. Una costante in fase di compilazione avrà lo stesso valore ogni volta che viene eseguita un'applicazione, mentre una costante di runtime può cambiare ogni volta. Le costanti in fase di compilazione sono necessarie per i casi, ad esempio i limiti della matrice, le espressioni case o gli inizializzatori di enumeratore.  
  
## <a name="in-this-section"></a>In questa sezione  
  
|Definizione|Termine|  
|---|---|  
|[Procedura: Dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Viene illustrato come utilizzare il `Const` istruzione per dichiarare una costante e impostarne il valore; dichiarando una costante, si assegna un nome significativo al valore.|  
|[Costanti definite dall'utente](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Viene descritto come creare costanti personalizzate, incluse le informazioni sulla definizione dell'ambito e come evitare riferimenti circolari.|  
|[Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Vengono fornite informazioni sul modo in cui il compilatore Visual Basic consente di inizializzare le costanti quando `Option Explicit` è disattivata.|  
|[Procedura: Raggruppare i valori costanti correlate](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Viene illustrato come raggruppare i valori costanti che sono correlati.|  
  
## <a name="reference"></a>Riferimenti  
  
|Definizione|Termine|  
|---|---|  
|[Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Vengono elencate le costanti predefinite di Visual Basic.|  
|[Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)|Viene descritto il `Const` istruzione e sul relativo uso.|  
|[Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Viene descritto il `Option Strict` istruzione e sul relativo uso.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Procedura: Inizializzare una variabile di matrice in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
