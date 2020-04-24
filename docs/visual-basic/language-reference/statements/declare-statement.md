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
ms.openlocfilehash: 9895709076634ce156ba9d1009f79ba7ddd2ba56
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646376"
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
|`attributelist`|Facoltativa. Vedere [Elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|
|`accessmodifier`|Facoltativa. Può essere uno dei valori seguenti:<br /><br /> -   [Pubblico](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Amico](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privato](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Amico protetto](../../language-reference/modifiers/protected-friend.md)<br />- [Privato Protetto](../../language-reference/modifiers/private-protected.md)<br /><br /> Vedere [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Facoltativa. Consultate [Ombre](../../../visual-basic/language-reference/modifiers/shadows.md).|
|`charsetmodifier`|Facoltativa. Specifica il set di caratteri e le informazioni di ricerca dei file. Può essere uno dei valori seguenti:<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) (predefinito)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Automatico](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|Facoltativo, `Sub` ma `Function` deve essere visualizzato o . Indica che la procedura esterna non restituisce un valore.|
|`Function`|Facoltativo, `Sub` ma `Function` deve essere visualizzato o . Indica che la routine esterna restituisce un valore.|
|`name`|Obbligatorio. Nome di questo riferimento esterno. Per ulteriori informazioni, vedere [Nomi degli elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Obbligatorio. Introduce una `Lib` clausola, che identifica il file esterno (DLL o risorsa di codice) che contiene una routine esterna.|
|`libname`|Obbligatorio. Nome del file che contiene la routine dichiarata.|
|`Alias`|Facoltativa. Indica che la routine dichiarata non può essere identificata `name`all'interno del file con il nome specificato in . Specificare la `aliasname`sua identificazione in .|
|`aliasname`|Obbligatorio se si `Alias` utilizza la parola chiave. Stringa che identifica la procedura in uno dei due modi seguenti:<br /><br /> Il nome del punto di ingresso della routine`""`all'interno del relativo file, racchiuso tra virgolette ( )<br /><br /> -oppure-<br /><br /> Un simbolo`#`di cancelno ( ) seguito da un numero intero che specifica il numero ordinale del punto di ingresso della routine all'interno del relativo file|
|`parameterlist`|Obbligatorio se la procedura accetta parametri. Vedere [Elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|
|`returntype`|Obbligatorio `Function` se è `Option Strict` `On`specificato ed è . Tipo di dati del valore restituito dalla routine.|

## <a name="remarks"></a>Osservazioni

In alcuni casi è necessario chiamare una routine definita in un file (ad esempio una DLL o una risorsa di codice) all'esterno del progetto. In questo caso, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la routine, ad esempio dove si trova la routine, come viene identificata, la sequenza di chiamata e il tipo restituito e il set di caratteri di stringa che utilizza. L'istruzione `Declare` crea un riferimento a una routine esterna e fornisce le informazioni necessarie.

Si può usare `Declare` solo a livello di modulo. Ciò significa che il contesto della *dichiarazione* per un riferimento esterno deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

L'impostazione predefinita dei riferimenti esterni è [Accesso pubblico.](../../../visual-basic/language-reference/modifiers/public.md) È possibile regolare i livelli di accesso con i modificatori di accesso.

## <a name="rules"></a>Regole

- **Attributi.** È possibile applicare attributi a un riferimento esterno. Qualsiasi attributo applicato ha effetto solo nel progetto, non nel file esterno.

- **Modificatori.** Le procedure esterne sono implicitamente [condivise](../../../visual-basic/language-reference/modifiers/shared.md). Non è `Shared` possibile utilizzare la parola chiave quando si dichiara un riferimento esterno e non è possibile modificarne lo stato condiviso.

  Una routine esterna non può partecipare all'override, implementare membri di interfaccia o gestire eventi. Di conseguenza, non `Overrides` `Overridable`è `NotOverridable` `MustOverride`possibile `Implements`utilizzare `Handles` la `Declare` parola chiave , , , , o in un'istruzione .

- **Nome procedura esterna.** Non è necessario assegnare a questo riferimento `name`esterno lo stesso nome (in ) del`aliasname`nome del punto di ingresso della routine all'interno del relativo file esterno ( ). È possibile `Alias` utilizzare una clausola per specificare il nome del punto di ingresso. Ciò può essere utile se la routine esterna ha lo stesso nome di un modificatore riservato di Visual Basic o di una variabile, una routine o qualsiasi altro elemento di programmazione nello stesso ambito.

  > [!NOTE]
  > Per i nomi dei punti di ingresso nella maggior parte delle DLL viene fatta distinzione tra maiuscole e minuscole.

- **Numero di procedura esterno.** In alternativa, è `Alias` possibile utilizzare una clausola per specificare il numero ordinale del punto di ingresso all'interno della tabella di esportazione del file esterno. A tale scopo, `aliasname` iniziare con`#`un simbolo di cancelno ( ). Ciò può essere utile se qualsiasi carattere nel nome della routine esterna non è consentito in Visual Basic o se il file esterno esporta la routine senza un nome.

## <a name="data-type-rules"></a>Regole del tipo di datiData Type Rules

- **Tipi di dati dei parametri.** Se `Option Strict` `On`è , è necessario specificare `parameterlist`il tipo di dati di ciascun parametro in . Può trattarsi di qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia. All'interno `parameterlist`di `As` , si utilizza una clausola per specificare il tipo di dati dell'argomento da passare a ogni parametro.

  > [!NOTE]
  > Se la routine esterna non è stata scritta per .NET Framework, è necessario fare attenzione che corrispondano i tipi di dati. Ad esempio, se si dichiara un riferimento esterno a `Integer` una routine di Visual Basic 6.0 con un parametro `Short` (16 bit in Visual Basic 6.0), è necessario identificare l'argomento corrispondente come nell'istruzione `Declare` , poiché si tratta del tipo Integer a 16 bit in Visual Basic. Analogamente, `Long` ha una larghezza di dati diversa `Date` in Visual Basic 6.0 e viene implementato in modo diverso.

- **Tipo di dati restituito.** Se la routine `Function` esterna `Option Strict` `On`è e , è necessario specificare il tipo di dati del valore restituito al codice chiamante. Può trattarsi di qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.

  > [!NOTE]
  > Il compilatore Visual Basic non verifica che i tipi di dati siano compatibili con quelli della routine esterna. In caso di mancata corrispondenza, Common <xref:System.Runtime.InteropServices.MarshalDirectiveException> Language Runtime genera un'eccezione in fase di esecuzione.

- **Tipi di dati predefiniti.** Se `Option Strict` `Off` è e non si specifica il `parameterlist`tipo di dati di un parametro in , il compilatore Visual Basic converte l'argomento corrispondente nel [tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md). Analogamente, se non `returntype`si specifica , il compilatore accetta il tipo di dati restituito come `Object`.

  > [!NOTE]
  > Poiché si ha a che fare con una procedura esterna che potrebbe essere stata scritta su una piattaforma diversa, è pericoloso fare qualsiasi ipotesi sui tipi di dati o per consentire loro di default. È molto più sicuro specificare il tipo di dati di ogni parametro e del valore restituito, se presente. In questo modo si migliora anche la leggibilità del codice.

## <a name="behavior"></a>Comportamento

- **Ambito.** Un riferimento esterno si trova nell'ambito della classe, della struttura o del modulo.

- **Vita.** Un riferimento esterno ha la stessa durata della classe, struttura o modulo in cui è dichiarato.

- **Chiamata di una routine esterna.** Una routine esterna viene chiamata nello `Function` `Sub` stesso modo in cui si chiama una routine o , utilizzandola in un'espressione se restituisce un valore o specificandola in un'istruzione [Call](../../../visual-basic/language-reference/statements/call-statement.md) se non restituisce un valore.

  Gli argomenti vengono passati alla `parameterlist` routine `Declare` esterna esattamente come specificato da nell'istruzione. Non prendere in considerazione il modo in cui i parametri sono stati originariamente dichiarati nel file esterno. Analogamente, se è presente un valore restituito, utilizzarlo esattamente come specificato da `returntype` nell'istruzione `Declare` .

- **Set di caratteri.** È possibile `charsetmodifier` specificare come Visual Basic deve eseguire il marshalling delle stringhe quando chiama la routine esterna. Il `Ansi` modificatore indica a Visual Basic di effettuare `Unicode` il marshalling di tutte le stringhe in valori ANSI e il modificatore per eseguire il marshalling di tutte le stringhe in valori Unicode. Il `Auto` modificatore indica a Visual Basic di eseguire il marshalling delle stringhe in base alle regole di .NET Framework in base al riferimento `name`esterno o, `aliasname` se specificato. Il valore predefinito è `Ansi`.

  `charsetmodifier`specifica inoltre il modo in cui Visual Basic deve cercare la routine esterna all'interno del relativo file esterno. `Ansi`ed `Unicode` entrambi dirigono Visual Basic per cercarlo senza modificarne il nome durante la ricerca. `Auto`indica a Visual Basic di determinare il set di caratteri di base della piattaforma di runtime ed eventualmente modificare il nome della routine esterna, come indicato di seguito:

  - In una piattaforma ANSI, ad esempio Windows 95, Windows 98 o Windows Millennium Edition, cercare innanzitutto la procedura esterna senza alcuna modifica del nome. Se l'operazione non riesce, aggiungere "A" alla fine del nome della routine esterna e cercarla di nuovo.

  - In una piattaforma Unicode, ad esempio Windows NT, Windows 2000 o Windows XP, cercare innanzitutto la procedura esterna senza alcuna modifica del nome. Se l'operazione non riesce, aggiungere "W" alla fine del nome della routine esterna e cercarla di nuovo.

- **Meccanismo.** Visual Basic utilizza il meccanismo pInvoke *(Platform Invoke)* di .NET Framework per risolvere e accedere a routine esterne. L'istruzione `Declare` <xref:System.Runtime.InteropServices.DllImportAttribute> e la classe utilizzano entrambi questo meccanismo automaticamente e non è necessaria alcuna conoscenza di PInvoke. Per ulteriori informazioni, vedere [Procedura dettagliata: chiamata di API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Se la routine esterna viene eseguita all'esterno di Common Language Runtime (CLR), si tratta di *codice non gestito.* Quando si chiama una routine di questo tipo, ad esempio una funzione API di Windows o un metodo COM, è possibile esporre l'applicazione a rischi per la sicurezza. Per ulteriori informazioni, vedere Linee guida per la [codifica sicura per il codice non gestito](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato `Function` un riferimento esterno a una routine che restituisce il nome utente corrente. Chiama quindi la `GetUserNameA` procedura esterna `getUser` come parte della procedura.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Esempio

L'oggetto <xref:System.Runtime.InteropServices.DllImportAttribute> fornisce un modo alternativo di utilizzare le funzioni nel codice non gestito. Nell'esempio seguente viene dichiarata una `Declare` funzione importata senza utilizzare un'istruzione .

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Procedura dettagliata: chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
