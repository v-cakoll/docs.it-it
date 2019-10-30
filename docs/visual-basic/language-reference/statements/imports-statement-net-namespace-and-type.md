---
title: Istruzione Imports-tipo e spazio dei nomi .NET (Visual Basic)
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
ms.openlocfilehash: 573bb7383b292e0ad2e85a4355d89cf92fe8dd7d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040731"
---
# <a name="imports-statement-net-namespace-and-type"></a>Istruzione Imports (tipo e spazio dei nomi .NET)

Consente di fare riferimento ai nomi dei tipi senza qualifica dello spazio dei nomi.

## <a name="syntax"></a>Sintassi

```vb
Imports [ aliasname = ] namespace
' -or-
Imports [ aliasname = ] namespace.element
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`aliasname`|Parametro facoltativo. *Alias di importazione* o nome con cui il codice può fare riferimento a `namespace` anziché alla stringa di qualificazione completa. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`namespace`|Obbligatorio. Nome completo dello spazio dei nomi importato. Può essere una stringa di spazi dei nomi annidati a qualsiasi livello.|
|`element`|Parametro facoltativo. Nome di un elemento di programmazione dichiarato nello spazio dei nomi. Può essere qualsiasi elemento contenitore.|

## <a name="remarks"></a>Note

L'istruzione `Imports` consente di fare riferimento direttamente ai tipi contenuti in un determinato spazio dei nomi.

È possibile specificare un singolo nome di spazio dei nomi o una stringa di spazi dei nomi annidati. Ogni spazio dei nomi annidato è separato dallo spazio dei nomi di livello superiore successivo per un punto (`.`), come illustrato nell'esempio seguente:

```vb
Imports System.Collections.Generic
```

Ogni file di origine può contenere un numero qualsiasi di istruzioni `Imports`. Devono seguire qualsiasi dichiarazione di opzione, ad esempio l'istruzione `Option Strict`, e devono precedere qualsiasi dichiarazione di elemento di programmazione, ad esempio `Module` o istruzioni `Class`.

È possibile utilizzare `Imports` solo a livello di file. Ciò significa che il contesto di dichiarazione per l'importazione deve essere un file di origine e non può essere uno spazio dei nomi, una classe, una struttura, un modulo, un'interfaccia, una routine o un blocco.

Si noti che l'istruzione `Imports` non rende disponibili gli elementi di altri progetti e assembly per il progetto. L'importazione non comporta l'impostazione di un riferimento. Rimuove solo la necessità di qualificare i nomi già disponibili per il progetto. Per ulteriori informazioni, vedere "importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

> [!NOTE]
> È possibile definire istruzioni `Imports` implicite usando la [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Per ulteriori informazioni, vedere [procedura: aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).

## <a name="import-aliases"></a>Alias di importazione

Un *alias di importazione* definisce l'alias per uno spazio dei nomi o un tipo. Gli alias di importazione sono utili quando è necessario usare elementi con lo stesso nome dichiarati in uno o più spazi dei nomi. Per ulteriori informazioni e un esempio, vedere "qualificazione di un nome di elemento" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

Non dichiarare un membro a livello di modulo con lo stesso nome `aliasname`. In tal caso, il compilatore Visual Basic utilizza `aliasname` solo per il membro dichiarato e non lo riconosce più come alias di importazione.

Sebbene la sintassi utilizzata per dichiarare un alias di importazione sia simile a quella utilizzata per l'importazione di un prefisso dello spazio dei nomi XML, i risultati sono diversi. Un alias di importazione può essere usato come espressione nel codice, mentre un prefisso dello spazio dei nomi XML può essere usato solo nei valori letterali XML o nelle proprietà Axis XML come prefisso per un nome di attributo o di elemento completo.

### <a name="element-names"></a>Nomi di elementi

Se si fornisce `element`, deve rappresentare un *elemento contenitore*, ovvero un elemento di programmazione che può contenere altri elementi. Gli elementi contenitore includono classi, strutture, moduli, interfacce ed enumerazioni.

L'ambito degli elementi resi disponibili da un'istruzione `Imports` varia a seconda che si specifichino `element`. Se si specificano solo `namespace`, tutti i membri denominati in modo univoco dello spazio dei nomi e i membri degli elementi contenitore all'interno di tale spazio dei nomi sono disponibili senza qualificazione. Se si specificano sia `namespace` che `element`, solo i membri di tale elemento saranno disponibili senza qualificazione.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono restituite tutte le cartelle nella directory *C:\\* usando la classe <xref:System.IO.DirectoryInfo>:

Il codice non include istruzioni `Imports` all'inizio del file. Pertanto, i riferimenti <xref:System.IO.DirectoryInfo>, <xref:System.Text.StringBuilder>e <xref:Microsoft.VisualBasic.ControlChars.CrLf> sono tutti completi con gli spazi dei nomi.

[!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]

## <a name="example"></a>Esempio

Nell'esempio seguente vengono incluse `Imports` istruzioni per gli spazi dei nomi a cui si fa riferimento. Pertanto, non è necessario che i tipi siano completi con gli spazi dei nomi.

[!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]

[!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]
  
## <a name="example"></a>Esempio

Nell'esempio seguente vengono incluse `Imports` istruzioni che consentono di creare alias per gli spazi dei nomi a cui si fa riferimento. I tipi sono qualificati con gli alias.

[!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]

[!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]

## <a name="example"></a>Esempio

Nell'esempio seguente vengono incluse `Imports` istruzioni che consentono di creare alias per i tipi a cui si fa riferimento. Gli alias vengono utilizzati per specificare i tipi.

[!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]

[!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Namespace](namespace-statement.md)
- [Spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [Riferimenti e istruzione Imports](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Istruzione Imports (spazio dei nomi XML)](imports-statement-xml-namespace.md)
- [Riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
