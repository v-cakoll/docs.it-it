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
ms.openlocfilehash: bc6949c7b52e87b7b39dd2690cac915a5f0d15aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
|`attributelist`|Facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Pubblica](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privato](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Facoltativo. Specifica di set di caratteri e i file di informazioni di ricerca. Può essere uno dei seguenti:<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (impostazione predefinita)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Automatico](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Parametro facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Indica che la routine esterna non restituisce un valore.|  
|`Function`|Parametro facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Indica che la routine esterna restituisce un valore.|  
|`name`|Obbligatorio. Nome del riferimento esterno. Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Obbligatorio. Introduce un `Lib` clausola che identifica il file esterno (DLL o risorsa codice) contenente una routine esterna.|  
|`libname`|Obbligatorio. Nome del file che contiene la routine dichiarata.|  
|`Alias`|Facoltativo. Indica che la routine viene dichiarata non può essere identificata all'interno del file con il nome specificato `name`. Specificarne l'identificazione in `aliasname`.|  
|`aliasname`|Obbligatorio se si usa il `Alias` (parola chiave). Stringa che identifica la procedura descritta in uno dei due modi:<br /><br /> Il nome del punto di ingresso della routine all'interno del file, all'interno di virgolette doppie (`""`)<br /><br /> oppure<br /><br /> Un simbolo di cancelletto (`#`) seguito da un numero intero che specifica il numero ordinale del punto di ingresso della routine all'interno del file|  
|`parameterlist`|Obbligatorio se la procedura accetta parametri. Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Obbligatorio se `Function` specificato e `Option Strict` è `On`. Tipo di dati del valore restituito dalla routine.|  
  
## <a name="remarks"></a>Note  
 In alcuni casi è necessario chiamare una routine definita in un file (ad esempio una DLL o risorsa codice) all'esterno del progetto. Quando si esegue questa operazione, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la routine, ad esempio in cui si trova la procedura, come viene identificato, la sequenza di chiamata e tipo restituito e il set di caratteri della stringa che viene utilizzata. Il `Declare` istruzione crea un riferimento a una routine esterna e fornisce le informazioni necessarie.  
  
 Si può usare `Declare` solo a livello di modulo. Ciò significa che il *contesto della dichiarazione* per un riferimento esterno deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi, interfaccia, routine o blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Per impostazione predefinita a riferimenti esterni [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso. È possibile regolare i livelli di accesso con i modificatori di accesso.  
  
## <a name="rules"></a>Regole  
  
-   **Attributi.** È possibile applicare attributi a un riferimento esterno. Tutti gli attributi applicati hanno effetto solo nel progetto, non nel file esterno.  
  
-   **Modificatori.** Routine esterne sono implicitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Non è possibile utilizzare il `Shared` (parola chiave) quando si dichiara un riferimento esterno se non è possibile modificare lo stato condiviso.  
  
     Una routine esterna non può partecipare a viene sottoposto a override, implementare i membri di interfaccia o gestire gli eventi. Di conseguenza, è possibile utilizzare il `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, o `Handles` parola chiave in un `Declare` istruzione.  
  
-   **Nome della routine esterna.** Non è necessario assegnare lo stesso nome di riferimento esterno (in `name`) come nome del punto di ingresso della routine all'interno del file esterno (`aliasname`). È possibile utilizzare un `Alias` clausola per specificare il nome del punto di ingresso. Questo può essere utile se la routine esterna include un modificatore di Visual Basic riservato o una variabile, routine o altri elementi di programmazione lo stesso nome nello stesso ambito.  
  
    > [!NOTE]
    >  I nomi di punto di ingresso nella DLL la maggior parte delle maiuscole e minuscole.  
  
-   **Numero di routine esterna.** In alternativa, è possibile utilizzare un `Alias` clausola per specificare il numero ordinale del punto di ingresso all'interno della tabella di esportazione del file esterno. A tale scopo, iniziare `aliasname` con un simbolo di cancelletto (`#`). Può essere utile se qualsiasi carattere nel nome della routine esterna non è consentito in Visual Basic o file esterno Esporta la procedura senza nome.  
  
## <a name="data-type-rules"></a>Regole di tipo di dati  
  
-   **Tipi di dati di parametro.** Se `Option Strict` è `On`, è necessario specificare il tipo di dati di ogni parametro nella `parameterlist`. Può trattarsi di qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia. All'interno di `parameterlist`, si utilizza un `As` clausola per specificare il tipo di dati dell'argomento deve essere passato a ogni parametro.  
  
    > [!NOTE]
    >  Se la routine esterna non è stato scritto per .NET Framework, è necessario prestare attenzione i tipi di dati corrispondenti. Ad esempio, se si dichiara un riferimento esterno a una routine di Visual Basic 6.0 con un `Integer` parametro (16 bit in Visual Basic 6.0), è necessario identificare l'argomento corrispondente come `Short` nel `Declare` istruzione, perché è di 16 bit di tipo integer in Visual Basic. Analogamente, `Long` ha una larghezza di dati diversi in Visual Basic 6.0 e `Date` viene implementato in modo diverso.  
  
-   **Tipo di dati restituito.** Se la routine esterna è un `Function` e `Option Strict` è `On`, è necessario specificare il tipo di dati del valore restituito al codice chiamante. Può trattarsi di qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.  
  
    > [!NOTE]
    >  Il compilatore Visual Basic non verifica che i tipi di dati compatibili con quelli della routine esterna. Se è presente una mancata corrispondenza, common language runtime genera un <xref:System.Runtime.InteropServices.MarshalDirectiveException> eccezione in fase di esecuzione.  
  
-   **Tipi di dati predefiniti.** Se `Option Strict` è `Off` e non si specifica il tipo di dati di un parametro in `parameterlist`, il compilatore Visual Basic converte l'argomento corrispondente per il [tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md). Analogamente, se non si specifica `returntype`, il compilatore prende il tipo di dati restituito da `Object`.  
  
    > [!NOTE]
    >  Poiché si sta utilizzando una routine esterna che sia stato scritto su una piattaforma diversa, è pericoloso per fare supposizioni sui tipi di dati o per consentire loro di predefinito. È molto più sicuro specificare il tipo di dati di ogni parametro e il valore restituito, se presente. Inoltre, per migliorare la leggibilità del codice.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Ambito.** Un riferimento esterno è nell'ambito in tutta la classe, struttura o modulo.  
  
-   **Durata.** Un riferimento esterno è uguale alla durata della classe, una struttura o un modulo in cui viene dichiarato.  
  
-   **La chiamata a una routine esterna.** Si chiama una routine esterna esattamente come si chiama un `Function` o `Sub` procedura, dall'utilizzo in un'espressione restituisce un valore o specificando in un [istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md) se non restituisce un valore.  
  
     Passare argomenti per la routine esterna esattamente come specificato da `parameterlist` nel `Declare` istruzione. Non considerare come i parametri sono stati originariamente dichiarati nel file esterno. Analogamente, se è presente un valore restituito, usarlo esattamente come specificato da `returntype` nel `Declare` istruzione.  
  
-   **Set di caratteri.** È possibile specificare in `charsetmodifier` come Visual Basic deve effettuare il marshalling delle stringhe quando chiama la routine esterna. Il `Ansi` modificatore indica di effettuare il marshalling di tutte le stringhe in valori ANSI e `Unicode` modificatore indirizza per effettuare il marshalling di tutte le stringhe in valori Unicode. Il `Auto` indirizza il modificatore di Visual Basic per il marshalling di stringhe in base a .NET Framework delle regole in base al riferimento esterno `name`, o `aliasname` se specificato. Il valore predefinito è `Ansi`.  
  
     `charsetmodifier` Specifica inoltre come Visual Basic deve cercare la routine esterna all'interno del file esterno. `Ansi` e `Unicode` entrambi indirizzare Visual Basic per cercare senza modificarne il nome durante la ricerca. `Auto` indirizza Visual Basic per determinare il set di caratteri di base della piattaforma in fase di esecuzione ed eventualmente modificare il nome della routine esterna, come indicato di seguito:  
  
    -   In una piattaforma ANSI, ad esempio Windows 95, Windows 98 o Windows Millennium Edition, cercare innanzitutto la routine esterna senza modificarne il nome. Se il problema persiste, aggiungere "A" alla fine del nome della routine esterna e cercare nuovamente.  
  
    -   In una piattaforma di Unicode, ad esempio Windows NT, Windows 2000 o Windows XP, cercare innanzitutto la routine esterna senza modificarne il nome. Se il problema persiste, aggiungere "W" alla fine della routine esterna denominare e cercare nuovamente.  
  
-   **Meccanismo.** Visual Basic Usa .NET Framework *PInvoke* meccanismo (PInvoke) per risolvere e accedere alle routine esterne. Il `Declare` istruzione e <xref:System.Runtime.InteropServices.DllImportAttribute> classe entrambi utilizzano questo meccanismo automaticamente e non è necessaria la conoscenza di PInvoke. Per ulteriori informazioni, vedere [procedura dettagliata: chiamata di API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Se la routine esterna viene eseguito all'esterno di common language runtime (CLR), è *codice non gestito*. Quando si chiama una procedura, ad esempio una funzione API Win32 o un metodo COM, si potrebbe esporre l'applicazione a rischi di sicurezza. Per ulteriori informazioni, vedere [Secure linee guida di codifica per il codice non gestito](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato un riferimento esterno a un `Function` procedure che restituisce il nome utente corrente. Quindi chiama la routine esterna `GetUserNameA` come parte di `getUser` procedura.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Runtime.InteropServices.DllImportAttribute> fornisce un'alternativa all'utilizzo di funzioni in codice non gestito. Nell'esempio seguente viene dichiarata una funzione importata senza utilizzare un `Declare` istruzione.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Elenco dei parametri](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
