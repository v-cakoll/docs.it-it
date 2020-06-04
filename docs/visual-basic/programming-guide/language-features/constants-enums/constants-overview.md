---
title: Cenni preliminari sulle costanti
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: f45cb12c6ef0f90b9c90190f30ce8600fec80947
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414518"
---
# <a name="constants-overview-visual-basic"></a>Cenni preliminari sulle costanti (Visual Basic)
Una costante è un nome significativo che prende il posto di un numero o di una stringa che non cambia. Le costanti archiviano i valori che, come implica il nome, rimangono invariati durante l'esecuzione di un'applicazione. È possibile migliorare notevolmente la leggibilità del codice e renderlo più semplice da gestire usando le costanti. Usarli nel codice che contiene i valori che vengono nuovamente visualizzati o che dipendono da determinati numeri difficili da ricordare o che non hanno un significato ovvio.  
  
## <a name="how-to-create-and-use-constants"></a>Come creare e usare le costanti  
 Visual Basic contiene una serie di costanti predefinite, utilizzate principalmente per la stampa e la visualizzazione. È anche possibile creare costanti personalizzate con l' `Const` istruzione, usando le stesse linee guida per la creazione di un nome di variabile. Se `Option Strict` è `On` , è necessario dichiarare in modo esplicito il tipo di costante.  
  
 L'ambito di una costante, ovvero il set di tutto il codice che può farvi riferimento senza qualificare il nome, è uguale a quello di una variabile dichiarata nella stessa posizione. Per creare una costante esistente nell'ambito di una determinata procedura, dichiararla all'interno di tale procedura. Per creare una costante disponibile in un'applicazione, dichiararla usando la `Public` parola chiave nella sezione delle dichiarazioni della classe.  
  
> [!NOTE]
> Sebbene le costanti siano simili alle variabili, non è possibile modificarle o assegnarvi nuovi valori come si può fare per le variabili.  
  
 Le costanti utilizzate nel codice possono essere definite dal modello a oggetti per i controlli o i componenti che si utilizzano oppure possono essere definiti dall'utente, ovvero quelli creati personalmente.  
  
## <a name="compile-time-and-run-time-constants"></a>Costanti in fase di compilazione e in fase di esecuzione  
 Una costante in fase di compilazione viene calcolata al momento della compilazione del codice, mentre una costante in fase di esecuzione può essere calcolata solo mentre l'applicazione è in esecuzione. Una costante in fase di compilazione avrà lo stesso valore ogni volta che viene eseguita un'applicazione, mentre una costante in fase di esecuzione può cambiare ogni volta. Le costanti in fase di compilazione sono necessarie per casi quali i limiti della matrice, le espressioni del case o gli inizializzatori di enumeratori.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
|Definizione|Termine|  
|---|---|  
|[Procedura: dichiarare una costante](how-to-declare-a-constant.md)|Viene illustrato come utilizzare l' `Const` istruzione per dichiarare una costante e impostarne il valore; dichiarando una costante, si assegna un nome significativo al valore.|  
|[Costanti definite dall'utente](user-defined-constants.md)|Viene descritto come creare costanti personalizzate, incluse informazioni sull'ambito e come evitare riferimenti circolari.|  
|[Tipi di dati costanti e letterali](constant-and-literal-data-types.md)|Vengono fornite informazioni sul modo in cui il compilatore di Visual Basic inizializza le costanti quando `Option Explicit` è disattivato.|  
|[Procedura: raggruppare i valori delle costanti correlate](how-to-group-related-constant-values-together.md)|Viene illustrato come raggruppare i valori costanti correlati.|  
  
## <a name="reference"></a>Informazioni di riferimento  
  
|Definizione|Termine|  
|---|---|  
|[Costanti ed enumerazioni](../../../language-reference/constants-and-enumerations.md)|Elenca le costanti predefinite da Visual Basic.|  
|[Istruzione Const](../../../language-reference/statements/const-statement.md)|Descrive l' `Const` istruzione e il relativo utilizzo.|  
|[Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)|Descrive l' `Option Strict` istruzione e il relativo utilizzo.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
- [Procedura: Inizializzare una variabile di matrice in Visual Basic](../arrays/how-to-initialize-an-array-variable.md)
