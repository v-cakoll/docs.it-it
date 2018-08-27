---
title: Istruzione Imports - Namespace .NET e il tipo (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: 0211438e8b4c02fead910dd7a32e0df9ed73ddc5
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925598"
---
# <a name="imports-statement-net-namespace-and-type"></a>Istruzione Imports (tipo e spazio dei nomi .NET)
Consente di digitare i nomi a cui fare riferimento senza qualifica dello spazio dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`aliasname`|Facoltativo. Un' *alias di importazione* o il nome mediante il quale il codice può fare riferimento a `namespace` anziché la stringa di qualificazione completo. Visualizzare [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Obbligatorio. Il nome completo dello spazio dei nomi da importare. Può essere una stringa di spazi dei nomi annidata a qualsiasi livello.|  
|`element`|Facoltativo. Il nome di un elemento di programmazione è dichiarato nello spazio dei nomi. Può essere qualsiasi elemento del contenitore.|  
  
## <a name="remarks"></a>Note  
 Il `Imports` istruzione consente i tipi che sono contenuti in un determinato spazio dei nomi a cui fare riferimento direttamente.  
  
 È possibile fornire un nome singolo spazio dei nomi o una stringa di spazi dei nomi annidati. Ogni spazio dei nomi annidato è delimitato da spazio dei nomi di livello superiore successivo da un punto (`.`), come illustrato nell'esempio seguente.  
  
 `Imports System.Collections.Generic`  
  
 Ogni file di origine può contenere un numero qualsiasi di `Imports` istruzioni. Questi devono seguire le dichiarazioni di opzione, ad esempio la `Option Strict` istruzione che devono precedere qualsiasi dichiarazione di elemento di programmazione, ad esempio `Module` o `Class` istruzioni.  
  
 È possibile usare `Imports` solo a livello di file. Ciò significa che il contesto della dichiarazione per l'importazione deve essere un file di origine e non può essere un spazio dei nomi, classe, struttura, modulo, interfaccia, routine o blocco.  
  
 Si noti che il `Imports` istruzione non rende disponibili elementi di altri progetti e assembly al progetto. Importazione non è un'alternativa all'impostazione di un riferimento. Rimuove solo la necessità per qualificare i nomi che sono già disponibili per il progetto. Per altre informazioni, vedere "Importazione di elementi contenitore" nella [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  È possibile definire implicita `Imports` istruzioni utilizzando il [riferimenti (pagina), creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Per altre informazioni, vedere [procedura: aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
## <a name="import-aliases"></a>Alias di importazione  
 Un' *alias di importazione* definisce l'alias per un tipo o dello spazio dei nomi. Gli alias di importazione sono utili quando è necessario usare gli elementi con lo stesso nome che vengono dichiarati in uno o più spazi dei nomi. Per altre informazioni e un esempio, vedere "Qualificare un nome di un elemento" nella [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Non è necessario dichiarare un membro al livello di modulo con lo stesso nome `aliasname`. Se non lo, il compilatore Visual Basic utilizza `aliasname` solo per il membro dichiarato e non sarà più lo riconosce come un alias di importazione.  
  
 Sebbene la sintassi usata per dichiarare un alias di importazione è uguale a quella utilizzata per l'importazione di un prefisso dello spazio dei nomi XML, i risultati sono diversi. Un alias di importazione è utilizzabile come espressione nel codice, mentre un prefisso dello spazio dei nomi XML può essere utilizzato solo in valori letterali XML o proprietà axis XML come prefisso per un elemento completo o il nome dell'attributo.  
  
### <a name="element-names"></a>Nomi di elementi  
 Se si specificano `element`, dovrà rappresentare un *elemento contenitore*, vale a dire un elemento di programmazione che può contenere altri elementi. Elementi contenitore includono classi, strutture, moduli, interfacce ed enumerazioni.  
  
 L'ambito degli elementi messe a disposizione da un `Imports` istruzione dipende dal fatto che vengano specificati `element`. Se si specifica solo `namespace`, tutto in modo univoco denominate membri dello spazio dei nomi e i membri degli elementi contenitore all'interno di tale spazio dei nomi, sono disponibili senza qualifica. Se si specificano entrambe `namespace` e `element`, solo i membri di tale elemento sono disponibili senza qualifica.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente restituisce tutte le cartelle nella directory c:\. utilizzando il <xref:System.IO.DirectoryInfo> classe.  
  
 Il codice non ha alcun `Imports` istruzioni all'inizio del file. Pertanto, il `DirectoryInfo`, <xref:System.Text.StringBuilder>, e <xref:Microsoft.VisualBasic.ControlChars.CrLf> riferimenti sono tutte completamente qualificati con gli spazi dei nomi.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente include `Imports` istruzioni per gli spazi dei nomi cui viene fatto riferimento. Di conseguenza, i tipi non sono necessario essere completo con gli spazi dei nomi.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente include `Imports` istruzioni che creano gli alias per gli spazi dei nomi cui viene fatto riferimento. I tipi sono qualificati con gli alias.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente include `Imports` istruzioni che creano gli alias dei tipi di riferimento. Gli alias vengono utilizzati per specificare i tipi.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
