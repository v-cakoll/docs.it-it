---
title: Ambito in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 6139af65958cefe43578f436204fa6836a71de0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917839"
---
# <a name="scope-in-visual-basic"></a>Ambito in Visual Basic
Il *ambito* di un elemento dichiarato è il set di tutto il codice che può fare riferimento ad esso senza il nome completo o renderlo disponibile tramite un [istruzione Imports (tipo e .NET Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md). Un elemento ambito può essere uno dei livelli seguenti:  
  
|Livello|Descrizione|  
|-----------|-----------------|  
|Ambito blocco|Disponibile solo all'interno del codice blocco in cui è dichiarata|  
|Ambito di procedura|Disponibile a tutto il codice all'interno della routine in cui è dichiarata|  
|Ambito del modulo|Disponibile a tutto il codice all'interno di modulo, classe o struttura in cui è dichiarata|  
|Ambito Namespace|Disponibile a tutto il codice nello spazio dei nomi in cui è dichiarata|  
  
 Questi livelli di ambito lo stato di avanzamento da più ristretto (blocco) per lo più largo presente (spazio dei nomi), dove *ambito più ristretto* significa che il set più piccolo di codice che può fare riferimento all'elemento senza qualifica. Per altre informazioni, vedere "Livelli di ambito" in questa pagina.  
  
## <a name="specifying-scope-and-defining-variables"></a>Che specifica l'ambito e definire le variabili  
 Specificare l'ambito di un elemento quando viene dichiarato. L'ambito può dipendere da fattori seguenti:  
  
- L'area in cui si dichiara l'elemento (blocco, procedure, modulo, classe o struttura)  
  
- Lo spazio dei nomi che contiene la dichiarazione dell'elemento  
  
- Il livello di accesso che è dichiarare per l'elemento  
  
 Prestare attenzione quando si definiscono le variabili con lo stesso nome ma con un ambito diverso, perché questa operazione può comportare risultati imprevisti. Per altre informazioni, vedere [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="levels-of-scope"></a>Livelli di ambito  
 È disponibile per tutta l'area in cui viene dichiarato un elemento di programmazione. Tutto il codice nella stessa area è possibile fare riferimento all'elemento senza il nome completo.  
  
### <a name="block-scope"></a>Ambito del blocco  
 Un blocco è un set di istruzioni racchiuse tra parentesi iniziale e finale di istruzioni di dichiarazione, come il seguente:  
  
- `Do` e `Loop`  
  
- `For` [`Each`] e `Next`  
  
- `If` e `End If`  
  
- `Select` e `End Select`  
  
- `SyncLock` e `End SyncLock`  
  
- `Try` e `End Try`  
  
- `While` e `End While`  
  
- `With` e `End With`  
  
 Se si dichiara una variabile all'interno di un blocco, è possibile usarlo solo all'interno del blocco. Nell'esempio seguente, l'ambito della variabile integer `cube` è il blocco tra `If` e `End If`, e non è possibile fare riferimento a `cube` quando esecuzione passa all'esterno del blocco.  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  Anche se l'ambito di una variabile è limitato a un blocco, la sua durata è ancora che dell'intera procedura. Se si immette il blocco più volte nel corso della procedura, ogni variabile del blocco mantiene il valore precedente. Per evitare risultati imprevisti in tal caso, è consigliabile inizializzare le variabili di blocco all'inizio del blocco.  
  
### <a name="procedure-scope"></a>Ambito di procedura  
 Un elemento dichiarato all'interno di una routine non è disponibile di fuori di tale procedura. Solo le procedure che contiene la dichiarazione può usarlo. Le variabili a questo livello sono anche noti come *variabili locali*. Vengono dichiarate con il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md), con o senza il [statico](../../../../visual-basic/language-reference/modifiers/static.md) (parola chiave).  
  
 Ambito routine e blocco sono strettamente correlati. Se si dichiara una variabile all'interno di una routine, ma all'esterno di qualsiasi blocco in questa procedura, è possibile considerare la variabile con ambito del blocco, in cui il blocco è l'intera procedura.  
  
> [!NOTE]
>  Tutti gli elementi locali, anche se sono `Static` le variabili sono privati per le procedure in cui vengono visualizzati. Non è possibile dichiarare un elemento utilizzando il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) (parola chiave) all'interno di una routine.  
  
### <a name="module-scope"></a>Ambito del modulo  
 Per praticità, il termine singolo *a livello di modulo* si applica equamente a moduli, le classi e strutture. È possibile dichiarare gli elementi a questo livello, inserendo l'istruzione di dichiarazione all'esterno di qualsiasi routine o un blocco, ma all'interno di modulo, classe o struttura.  
  
 Quando si crea una dichiarazione a livello di modulo, il livello di accesso che scelto determina l'ambito. Lo spazio dei nomi che contiene il modulo, classe o struttura interesserà anche l'ambito.  
  
 Gli elementi per cui si dichiara [privato](../../../../visual-basic/language-reference/modifiers/private.md) a livello di accesso sono disponibili per tutte le routine in tale modulo, ma non per il codice in un modulo diverso. Il `Dim` per impostazione predefinita a livello di modulo istruzione `Private` se non si usano le parole chiave a livello di accesso. È tuttavia possibile apportare il livello di ambito e l'accesso in modo più chiaro tramite il `Private` parola chiave nel `Dim` istruzione.  
  
 Nell'esempio seguente, tutte le procedure definite nel modulo possono fare riferimento alla variabile di stringa `strMsg`. Quando la seconda procedura viene chiamata, viene visualizzato il contenuto della variabile di stringa `strMsg` in una finestra di dialogo.  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### <a name="namespace-scope"></a>Ambito Namespace  
 Se si dichiara un elemento a livello di modulo, utilizzando il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) oppure [pubblico](../../../../visual-basic/language-reference/modifiers/public.md) (parola chiave), diventa disponibile a tutte le procedure in tutto lo spazio dei nomi in cui l'elemento viene dichiarato. Con la modifica seguente all'esempio precedente, la variabile stringa `strMsg` può essere indicato dal codice in qualsiasi punto nello spazio dei nomi della relativa dichiarazione.  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 L'ambito Namespace include spazi dei nomi annidati. Un elemento disponibile dall'interno di uno spazio dei nomi è anche disponibile dall'interno di qualsiasi spazio dei nomi annidato all'interno di tale spazio dei nomi.  
  
 Se il progetto non contiene alcuna [istruzione Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, tutti gli elementi di progetto è dello stesso spazio dei nomi. In questo caso, è possano pensare ambito dello spazio dei nomi come ambito del progetto. `Public` sono disponibili a qualsiasi progetto che fa riferimento a progetto anche gli elementi in un modulo, classe o struttura.  
  
## <a name="choice-of-scope"></a>Scelta dell'ambito  
 Quando si dichiara una variabile, è necessario tenere presente quanto riportato di seguito quando si sceglie il relativo ambito.  
  
### <a name="advantages-of-local-variables"></a>Vantaggi delle variabili locali  
 Le variabili locali sono un'ottima scelta per qualsiasi tipo di calcolo temporaneo per i motivi seguenti:  
  
- **Prevenzione dei conflitti di nome.** I nomi delle variabili locali non sono soggetti a conflitti. Ad esempio, è possibile creare varie procedure diverse che contiene una variabile denominata `intTemp`. Fino a quando le `intTemp` viene dichiarato come una variabile locale, ogni routine riconosce solo la propria versione di `intTemp`. Qualsiasi singola routine può modificare il valore nella propria locale `intTemp` senza influire sulla `intTemp` variabili in altre procedure.  
  
- **Utilizzo di memoria.** Le variabili locali utilizzano memoria solo mentre è in esecuzione di procedure. Questa memoria viene rilasciata quando viene restituito al codice chiamante. Al contrario, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) e [statico](../../../../visual-basic/language-reference/modifiers/static.md) variabili occupano risorse di memoria fino a quando non si arresta l'applicazione in esecuzione, quindi utilizzarle solo se necessario. *Le variabili di istanze* occupano memoria finché l'istanza continua a esistere, pertanto sono meno efficienti rispetto alle variabili locali, ma potenzialmente più efficienti `Shared` o `Static` variabili.  
  
### <a name="minimizing-scope"></a>Riduzione dell'ambito  
 In generale, quando si dichiara una variabile o costante, è buona norma apportare più brevi possibile l'ambito (ambito del blocco è il più ristretto). Ciò consente di risparmiare memoria e riduce al minimo le probabilità di codice erroneamente che fa riferimento alla variabile non corretta. Analogamente, è necessario dichiarare una variabile [statici](../../../../visual-basic/language-reference/modifiers/static.md) solo quando è necessario mantenere il valore tra le chiamate di procedura.  
  
## <a name="see-also"></a>Vedere anche

- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Procedura: Controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
