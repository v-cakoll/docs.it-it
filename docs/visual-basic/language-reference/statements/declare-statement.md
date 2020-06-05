---
title: Declare Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 021805508a8a053ccc8fab6f1013109bece4b6f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404771"
---
# <a name="declare-statement"></a>Declare Statement

Dichiara un riferimento a una routine implementata in un file esterno.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`attributelist`|Facoltativa. Vedere [elenco attributi](attribute-list.md).|
|`accessmodifier`|Facoltativa. Può essere uno dei seguenti:<br /><br /> -   [Pubblico](../modifiers/public.md)<br />-   [Protetto](../modifiers/protected.md)<br />-   [Amico](../modifiers/friend.md)<br />-   [Privata](../modifiers/private.md)<br />- [Amico protetto](../modifiers/protected-friend.md)<br />- [Privato protetto](../modifiers/private-protected.md)<br /><br /> Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Facoltativa. Vedere [Shadows](../modifiers/shadows.md).|
|`charsetmodifier`|Facoltativa. Specifica le informazioni sul set di caratteri e la ricerca di file. Può essere uno dei seguenti:<br /><br /> -   [ANSI](../modifiers/ansi.md) (impostazione predefinita)<br />-   [Unicode](../modifiers/unicode.md)<br />-   [Automatico](../modifiers/auto.md)|
|`Sub`|Facoltativo, ma `Sub` `Function` deve essere visualizzato o. Indica che la procedura esterna non restituisce alcun valore.|
|`Function`|Facoltativo, ma `Sub` `Function` deve essere visualizzato o. Indica che la procedura esterna restituisce un valore.|
|`name`|Obbligatorio. Nome del riferimento esterno. Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Obbligatorio. Introduce una `Lib` clausola che identifica il file esterno (dll o risorsa di codice) contenente una routine esterna.|
|`libname`|Obbligatorio. Nome del file che contiene la routine dichiarata.|
|`Alias`|Facoltativa. Indica che la routine dichiarata non può essere identificata all'interno del file in base al nome specificato in `name` . Specificare l'identificazione in `aliasname` .|
|`aliasname`|Obbligatorio se si usa la `Alias` parola chiave. Stringa che identifica la procedura in uno dei due modi seguenti:<br /><br /> Nome del punto di ingresso della routine all'interno del file, racchiuso tra virgolette ( `""` )<br /><br /> -oppure-<br /><br /> Un simbolo di cancelletto ( `#` ) seguito da un Integer che specifica il numero ordinale del punto di ingresso della routine all'interno del file|
|`parameterlist`|Obbligatorio se la procedura accetta parametri. Vedere [elenco di parametri](parameter-list.md).|
|`returntype`|Obbligatorio se `Function` è specificato e `Option Strict` è `On` . Tipo di dati del valore restituito dalla stored procedure.|

## <a name="remarks"></a>Commenti

In alcuni casi è necessario chiamare una routine definita in un file, ad esempio una DLL o una risorsa di codice, all'esterno del progetto. Quando si esegue questa operazione, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure, ad esempio la posizione in cui si trova la stored procedure, il modo in cui viene identificata, la sequenza chiamante e il tipo restituito e il set di caratteri stringa usato. L' `Declare` istruzione crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.

Si può usare `Declare` solo a livello di modulo. Ciò significa che il *contesto di dichiarazione* per un riferimento esterno deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

Riferimenti esterni per impostazione predefinita l'accesso [pubblico](../modifiers/public.md) . È possibile modificare i livelli di accesso con i modificatori di accesso.

## <a name="rules"></a>Regole

- **Attributi.** È possibile applicare attributi a un riferimento esterno. Tutti gli attributi applicati hanno effetto solo nel progetto e non nel file esterno.

- **Modificatori.** Le procedure esterne sono implicitamente [condivise](../modifiers/shared.md). Non è possibile usare la `Shared` parola chiave quando si dichiara un riferimento esterno e non è possibile modificarne lo stato condiviso.

  Una procedura esterna non può partecipare all'override, all'implementazione di membri di interfaccia o alla gestione degli eventi. Di conseguenza, non è possibile usare la `Overrides` `Overridable` parola chiave,, `NotOverridable` , `MustOverride` , `Implements` o `Handles` in un' `Declare` istruzione.

- **Nome della procedura esterna.** Non è necessario assegnare a questo riferimento esterno lo stesso nome (in `name` ) del nome del punto di ingresso della stored procedure all'interno del file esterno ( `aliasname` ). È possibile usare una `Alias` clausola per specificare il nome del punto di ingresso. Questo può essere utile se la procedura esterna ha lo stesso nome di un modificatore riservato Visual Basic o di una variabile, di una routine o di qualsiasi altro elemento di programmazione nello stesso ambito.

  > [!NOTE]
  > I nomi dei punti di ingresso nella maggior parte delle dll fanno distinzione tra maiuscole e minuscole

- **Numero di procedura esterna.** In alternativa, è possibile usare una `Alias` clausola per specificare il numero ordinale del punto di ingresso all'interno della tabella di esportazione del file esterno. A tale scopo, si inizia `aliasname` con un simbolo di cancelletto ( `#` ). Questo può essere utile se un carattere nel nome della procedura esterna non è consentito in Visual Basic o se il file esterno Esporta la stored procedure senza un nome.

## <a name="data-type-rules"></a>Regole del tipo di dati

- **Tipi di dati dei parametri.** Se `Option Strict` è `On` , è necessario specificare il tipo di dati di ogni parametro in `parameterlist` . Può essere qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia. In `parameterlist` è possibile utilizzare una `As` clausola per specificare il tipo di dati dell'argomento da passare a ogni parametro.

  > [!NOTE]
  > Se la procedura esterna non è stata scritta per la .NET Framework, è necessario prestare attenzione che i tipi di dati corrispondano. Se, ad esempio, si dichiara un riferimento esterno a una procedura Visual Basic 6,0 con un `Integer` parametro (16 bit in Visual Basic 6,0), è necessario identificare l'argomento corrispondente come `Short` nell' `Declare` istruzione, perché questo è il tipo Integer a 16 bit in Visual Basic. Analogamente, `Long` ha una larghezza di dati diversa in Visual Basic 6,0 ed `Date` è implementata in modo diverso.

- **Tipo di dati restituito.** Se la procedura esterna è `Function` e `Option Strict` è, è `On` necessario specificare il tipo di dati del valore restituito al codice chiamante. Può essere qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.

  > [!NOTE]
  > Il compilatore Visual Basic non verifica che i tipi di dati siano compatibili con quelli della procedura esterna. In caso di mancata corrispondenza, il Common Language Runtime genera un' <xref:System.Runtime.InteropServices.MarshalDirectiveException> eccezione in fase di esecuzione.

- **Tipi di dati predefiniti.** Se `Option Strict` è `Off` e non si specifica il tipo di dati di un parametro in `parameterlist` , il compilatore Visual Basic converte l'argomento corrispondente nel [tipo di dati Object](../data-types/object-data-type.md). Analogamente, se non si specifica `returntype` , il compilatore accetta il tipo di dati restituito come `Object` .

  > [!NOTE]
  > Poiché si tratta di una procedura esterna che potrebbe essere stata scritta su una piattaforma diversa, è pericoloso creare ipotesi sui tipi di dati o per consentirne l'impostazione predefinita. È molto più sicuro specificare il tipo di dati di ogni parametro e del valore restituito, se presente. Questa operazione migliora inoltre la leggibilità del codice.

## <a name="behavior"></a>Comportamento

- **Ambito.** Un riferimento esterno è nell'ambito di tutta la classe, la struttura o il modulo.

- **Vita.** Un riferimento esterno ha la stessa durata della classe, della struttura o del modulo in cui è dichiarata.

- **Chiamata a una routine esterna.** È possibile chiamare una routine esterna nello stesso modo in cui si chiama una `Function` routine o, `Sub` usandola in un'espressione se restituisce un valore o specificandone il valore in un' [istruzione Call](call-statement.md) se non restituisce un valore.

  Gli argomenti vengono passati alla procedura esterna esattamente come specificato `parameterlist` nell' `Declare` istruzione. Non prendere in considerazione il modo in cui i parametri sono stati originariamente dichiarati nel file esterno. Analogamente, se è presente un valore restituito, utilizzarlo esattamente come specificato da `returntype` nell' `Declare` istruzione.

- **Set di caratteri.** È possibile specificare in `charsetmodifier` che modo Visual Basic deve effettuare il marshalling delle stringhe quando chiama la routine esterna. Il `Ansi` modificatore indica Visual Basic di effettuare il marshalling di tutte le stringhe in valori ANSI e il `Unicode` modificatore lo indirizza per eseguire il marshalling di tutte le stringhe in valori Unicode. Il `Auto` modificatore indica Visual Basic di effettuare il marshalling delle stringhe in base alle regole di .NET Framework basate sul riferimento esterno `name` o, `aliasname` se specificato. Il valore predefinito è `Ansi`.

  `charsetmodifier`specifica anche il modo in cui Visual Basic deve cercare la procedura esterna all'interno del file esterno. `Ansi`ed `Unicode` entrambi Visual Basic direttamente per cercarli senza modificarne il nome durante la ricerca. `Auto`indica Visual Basic per determinare il set di caratteri di base della piattaforma di runtime ed eventualmente modificare il nome della procedura esterna, come indicato di seguito:

  - In una piattaforma ANSI, ad esempio Windows 95, Windows 98 o Windows Millennium Edition, cercare prima la procedura esterna senza modificarne il nome. Se l'operazione ha esito negativo, aggiungere "A" alla fine del nome della procedura esterna e cercarla nuovamente.

  - In una piattaforma Unicode, ad esempio Windows NT, Windows 2000 o Windows XP, cercare prima la procedura esterna senza modificarne il nome. Se l'operazione ha esito negativo, aggiungere "W" alla fine del nome della procedura esterna e cercarla nuovamente.

- **Meccanismo.** Visual Basic utilizza il meccanismo .NET Framework *Platform Invoke* (PInvoke) per risolvere e accedere a procedure esterne. L' `Declare` istruzione e la <xref:System.Runtime.InteropServices.DllImportAttribute> classe utilizzano entrambi questo meccanismo automaticamente e non è necessaria alcuna conoscenza di PInvoke. Per altre informazioni, vedere [procedura dettagliata: chiamata delle API di Windows](../../programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Se la procedura esterna viene eseguita all'esterno del Common Language Runtime (CLR), si tratta di *codice non gestito*. Quando si chiama una procedura di questo tipo, ad esempio una funzione API Windows o un metodo COM, è possibile esporre l'applicazione ai rischi per la sicurezza. Per altre informazioni, vedere [linee guida per la codifica di codice non gestito](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato un riferimento esterno a una `Function` routine che restituisce il nome utente corrente. Chiama quindi la procedura esterna `GetUserNameA` come parte della `getUser` procedura.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Esempio

<xref:System.Runtime.InteropServices.DllImportAttribute>Fornisce un metodo alternativo per l'utilizzo di funzioni nel codice non gestito. Nell'esempio seguente viene dichiarata una funzione importata senza usare un' `Declare` istruzione.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Istruzione Imports (tipo e spazio dei nomi .NET)](imports-statement-net-namespace-and-type.md)
- [Operatore AddressOf](../operators/addressof-operator.md)
- [Istruzione Function](function-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Elenco parametri](parameter-list.md)
- [Istruzione Call](call-statement.md)
- [Procedura dettagliata: Chiamata delle API di Windows](../../programming-guide/com-interop/walkthrough-calling-windows-apis.md)
