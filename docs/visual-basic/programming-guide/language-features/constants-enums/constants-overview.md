---
title: Cenni preliminari sulle costanti (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 2ec43254013df5444048b5197489c55217d5328a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648385"
---
# <a name="constants-overview-visual-basic"></a>Cenni preliminari sulle costanti (Visual Basic)
Una costante è un nome significativo che prende il posto di un numero o stringa che non cambia. Costanti di archiviano i valori, come suggerisce il nome, rimangono invariati durante l'esecuzione di un'applicazione. Notevolmente, è possibile migliorare la leggibilità del codice e rendere più semplice gestire l'utilizzo delle costanti. Utilizzarle nel codice che contiene valori che vengono ripetuti o che dipendono da alcuni numeri che sono difficili da ricordare o non hanno alcun significato ovvio.  
  
## <a name="how-to-create-and-use-constants"></a>Come creare e utilizzare le costanti  
 Visual Basic contiene un numero di costanti predefinite, utilizzate principalmente per la stampa e visualizzazione. È inoltre possibile creare costanti personalizzate con il `Const` istruzione, utilizzando le stesse linee guida per la creazione di un nome di variabile. Se `Option Strict` è `On`, è necessario dichiarare in modo esplicito il tipo di costante.  
  
 Ambito di una costante, ovvero il set di tutto il codice che è possibile farvi riferimento senza qualificarne il nome è uguale a quello di una variabile dichiarata nello stesso percorso. Per creare una costante che esista nell'ambito di una particolare procedura, eseguirne la dichiarazione all'interno di tale routine. Per creare una costante che sia disponibile un'applicazione, dichiararla utilizzando il `Public` (parola chiave) nella sezione delle dichiarazioni di classe.  
  
> [!NOTE]
>  Sebbene le costanti siano simili variabili, è possibile modificarle o assegnare di nuovi valori, come per le variabili.  
  
 Le costanti utilizzate nel codice possono essere definite dal modello a oggetti per i controlli o componenti utilizzati, o possono essere definite dall'utente (vale a dire quelli creato dall'utente).  
  
## <a name="compile-time-and-run-time-constants"></a>Costanti in fase di compilazione e Runtime  
 Al momento che il codice viene compilato, mentre una costante in fase di esecuzione può essere calcolata solo mentre l'applicazione è in esecuzione, viene calcolata una costante in fase di compilazione. Una costante in fase di compilazione avrà lo stesso valore ogni volta che viene eseguita un'applicazione, mentre una costante in fase di esecuzione potrebbe cambiare ogni volta. Costanti in fase di compilazione sono necessari per i casi, ad esempio i limiti di matrice, le espressioni case o gli inizializzatori di enumeratore.  
  
## <a name="in-this-section"></a>In questa sezione  
  
|Definizione|Termine|  
|---|---|  
|[Procedura: Dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Viene illustrato come utilizzare il `Const` istruzione per dichiarare una costante e impostarne il valore; dichiarando una costante, assegnare un nome significativo per il valore.|  
|[Costanti definite dall'utente](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Viene descritto come creare costanti personalizzate, incluse le informazioni sulla definizione dell'ambito e come evitare i riferimenti circolari.|  
|[Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Vengono fornite informazioni sul modo in cui il compilatore Visual Basic Inizializza le costanti quando `Option Explicit` è stato disattivato.|  
|[Procedura: Raggruppare i valori delle costanti correlate](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Viene illustrato come raggruppare i valori costanti che sono correlati.|  
  
## <a name="reference"></a>Riferimenti  
  
|Definizione|Termine|  
|---|---|  
|[Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Vengono elencate le costanti predefinite di Visual Basic.|  
|[Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)|Viene descritto il `Const` istruzione e sul relativo uso.|  
|[Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Viene descritto il `Option Strict` istruzione e sul relativo uso.|  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Procedura: Inizializzare una variabile di matrice in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
