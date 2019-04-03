---
title: Declare (istruzione) (Visual Basic)
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
ms.openlocfilehash: fbb7b4e118598157e2005469f89831df50de6576
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838339"
---
# <a name="declare-statement"></a>Declare Statement
Dichiara un riferimento a una routine implementata in un file esterno.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|`attributelist`|Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Private Protected](../../language-reference/modifiers/private-protected.md)<br /><br /> Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Facoltativo. Specifica di set di caratteri e i file di informazioni di ricerca. Può essere uno dei seguenti:<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (impostazione predefinita)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Automatico](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Indica che la routine esterna non restituisce un valore.|  
|`Function`|Facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Indica che la routine esterna restituisce un valore.|  
|`name`|Obbligatorio. Nome della Guida di riferimento esterno. Per altre informazioni, vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Obbligatorio. Introduce un `Lib` clausola che identifica il file esterno (DLL o risorsa codice) contenente una routine esterna.|  
|`libname`|Obbligatorio. Nome del file che contiene la routine dichiarata.|  
|`Alias`|Facoltativo. Indica che la routine viene dichiarata non può essere identificata all'interno del file per il nome specificato in `name`. Specificarne l'identificazione in `aliasname`.|  
|`aliasname`|Obbligatorio se si usa il `Alias` (parola chiave). Stringa che identifica la procedura descritta in uno dei due modi:<br /><br /> Il nome del punto di ingresso della routine all'interno del file, all'interno delle virgolette (`""`)<br /><br /> -oppure-<br /><br /> Un simbolo di cancelletto (`#`) seguito da un integer che specifica il numero ordinale del punto di ingresso della routine all'interno del file|  
|`parameterlist`|Obbligatorio se la procedura accetta parametri. Visualizzare [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Obbligatorio se `Function` specificato e `Option Strict` è `On`. Tipo di dati del valore restituito dalla procedura.|  
  
## <a name="remarks"></a>Note  
 In alcuni casi è necessario chiamare una routine definita in un file (ad esempio una DLL o risorsa codice) all'esterno del progetto. Quando si esegue questa operazione, il compilatore Visual Basic è privo di accesso per le informazioni necessarie per chiamare la routine in modo corretto, ad esempio in cui si trova la procedura, come viene identificato, la sequenza di chiamata e il tipo restituito e il set di caratteri della stringa che viene utilizzata. Il `Declare` istruzione crea un riferimento a una routine esterna e fornisce le informazioni necessarie.  
  
 Si può usare `Declare` solo a livello di modulo. Ciò significa che il *contesto della dichiarazione* per un riferimento esterno deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi, interfaccia, routine o blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Per impostazione predefinita a riferimenti esterni [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso. È possibile modificare i livelli di accesso con i modificatori di accesso.  
  
## <a name="rules"></a>Regole  
  
-   **Attributi.** È possibile applicare attributi a un riferimento esterno. Tutti gli attributi applicati hanno effetto solo nel progetto, non nel file esterno.  
  
-   **Modificatori.** Routine esterne sono implicitamente [condiviso](../../../visual-basic/language-reference/modifiers/shared.md). Non è possibile usare il `Shared` parola chiave quando si dichiara un riferimento esterno ed è possibile modificare lo stato condiviso.  
  
     Una routine esterna non possa partecipare a viene sottoposto a override, implementano membri di interfaccia o la gestione degli eventi. Di conseguenza, non è possibile usare la `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, oppure `Handles` parola chiave in un `Declare` istruzione.  
  
-   **Nome della routine esterna.** Non è necessario assegnare lo stesso nome di questo riferimento esterno (in `name`) come nome del punto di ingresso della stored procedure contenuta nel file esterno (`aliasname`). È possibile usare un `Alias` clausola per specificare il nome del punto di ingresso. Ciò può essere utile se la routine esterna ha lo stesso nome come modificatore riservato Visual Basic o una variabile, routine o altri elementi di programmazione nello stesso ambito.  
  
    > [!NOTE]
    >  I nomi di punto di ingresso in quasi tutte le DLL sono tra maiuscole e minuscole.  
  
-   **Numero di routine esterna.** In alternativa, è possibile usare un `Alias` clausola per specificare il numero ordinale del punto di ingresso all'interno della tabella di esportazione del file esterno. A tale scopo, iniziare `aliasname` con un simbolo di cancelletto (`#`). Ciò risulta utile se qualsiasi carattere nel nome della routine esterna non è consentito in Visual Basic o se il file esterno consente di esportare la procedura senza nome.  
  
## <a name="data-type-rules"></a>Regole di tipo di dati  
  
-   **Tipi di dati di parametro.** Se `Option Strict` viene `On`, è necessario specificare il tipo di dati di ogni parametro in `parameterlist`. Può trattarsi di qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia. All'interno `parameterlist`, si utilizza un `As` clausola per specificare il tipo di dati dell'argomento deve essere passato a ogni parametro.  
  
    > [!NOTE]
    >  Se la routine esterna non è stato scritto per .NET Framework, è necessario prestare attenzione i tipi di dati corrispondenti. Ad esempio, se si dichiara un riferimento esterno a una procedura di Visual Basic 6.0 con un' `Integer` parametro (16 bit in Visual Basic 6.0), è necessario identificare l'argomento corrispondente come `Short` nel `Declare` istruzione, perché questo è il 16 - tipo di integer bit in Visual Basic. Analogamente, `Long` ha un'ampiezza dei dati diversa in Visual Basic 6.0, e `Date` viene implementato in modo diverso.  
  
-   **Tipo di dati restituito.** Se la routine esterna è un `Function` e `Option Strict` è `On`, è necessario specificare il tipo di dati del valore restituito al codice chiamante. Può trattarsi di qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.  
  
    > [!NOTE]
    >  Il compilatore Visual Basic non verifica che i tipi di dati compatibili con quelli della routine esterna. Se è presente una mancata corrispondenza, common language runtime genera una <xref:System.Runtime.InteropServices.MarshalDirectiveException> eccezione in fase di esecuzione.  
  
-   **Tipi di dati predefiniti.** Se `Option Strict` viene `Off` e non si specifica il tipo di dati di un parametro in `parameterlist`, il compilatore Visual Basic consente di convertire l'argomento corrispondente per il [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md). Analogamente, se non si specifica `returntype`, il compilatore prende il tipo di dati restituito sia `Object`.  
  
    > [!NOTE]
    >  Poiché è necessario gestire una routine esterna che sia stato scritto su una piattaforma diversa, può essere pericoloso per fare supposizioni sui tipi di dati o per consentire loro di default. È molto più sicura specificare il tipo di dati di ogni parametro e il valore restituito, se presente. Inoltre, per migliorare la leggibilità del codice.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Ambito.** Un riferimento esterno è nell'ambito in tutta la classe, struttura o modulo.  
  
-   **Ciclo di vita.** Un riferimento esterno ha la stessa durata della classe, struttura o modulo in cui è dichiarata.  
  
-   **Chiamare una routine esterna.** Si chiama una routine esterna simile a quello di chiamare un `Function` oppure `Sub` procedure, ovvero utilizzandolo in un'espressione, se viene restituito un valore o specificando in un [istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md) se non viene restituito un valore.  
  
     È passare argomenti per la routine esterna esattamente come specificato da `parameterlist` nella `Declare` istruzione. Non considerare come i parametri sono stati originariamente dichiarati nel file esterno. Analogamente, se è presente un valore restituito, usarlo esattamente come specificato da `returntype` nella `Declare` istruzione.  
  
-   **Set di caratteri.** È possibile specificare in `charsetmodifier` come Visual Basic deve effettuare il marshalling delle stringhe quando chiama la routine esterna. Il `Ansi` modificatore indirizza il marshalling di tutte le stringhe in valori ANSI e `Unicode` modificatore indirizza per effettuare il marshalling di tutte le stringhe in valori Unicode. Il `Auto` modificatore indica a Visual Basic per il marshalling delle stringhe in base a .NET Framework delle regole in base al riferimento esterno `name`, o `aliasname` se non specificato. Il valore predefinito è `Ansi`.  
  
     `charsetmodifier` Specifica inoltre come Visual Basic deve cercare la routine esterna all'interno del file esterno. `Ansi` e `Unicode` entrambe indirizzare Visual Basic per cercare senza modificarne il nome durante la ricerca. `Auto` indica a Visual Basic per determinare il set di caratteri di base della piattaforma in fase di esecuzione ed eventualmente modificare il nome della routine esterna, come indicato di seguito:  
  
    -   In una piattaforma di ANSI, ad esempio Windows 95, Windows 98 o Windows Millennium Edition, cercare prima di tutto la routine esterna senza modificarne il nome. Se il problema persiste, aggiungere "A" alla fine del nome della routine esterna a cercare nuovamente.  
  
    -   In una piattaforma di Unicode, ad esempio Windows NT, Windows 2000 o Windows XP, cercare prima di tutto la routine esterna senza modificarne il nome. Se il problema persiste, aggiungere "W" alla fine della routine esterna assegnare un nome e cercare nuovamente.  
  
-   **Meccanismo.** Visual Basic Usa .NET Framework *PInvoke* meccanismo (PInvoke) per risolvere e accedere alle routine esterne. Il `Declare` istruzione e <xref:System.Runtime.InteropServices.DllImportAttribute> classe entrambi usano questo meccanismo automaticamente e non è necessaria alcuna conoscenza di una chiamata PInvoke. Per altre informazioni, vedere [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Se la routine esterna viene eseguito all'esterno di common language runtime (CLR), si tratta *codice non gestito*. Quando si chiama questo tipo una routine, ad esempio una funzione API di Windows o un metodo COM, si potrà esporre l'applicazione a rischi di sicurezza. Per altre informazioni, vedere [Secure linee guida di codifica per il codice non gestito](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente dichiara un riferimento esterno a un `Function` procedure che restituisce il nome dell'utente corrente. Quindi chiama la routine esterna `GetUserNameA` come parte di `getUser` procedure.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Runtime.InteropServices.DllImportAttribute> offre un modo alternativo all'utilizzo di funzioni nel codice non gestito. L'esempio seguente dichiara una funzione importata senza usare un `Declare` istruzione.  
  
 [!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Elenco dei parametri](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
