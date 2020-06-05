---
title: Istruzione Imports-spazio dei nomi XML
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: a3184d68b0e4cdff5d4296a5a638e22b4e83bcde
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404537"
---
# <a name="imports-statement-xml-namespace"></a>Istruzione Imports (spazio dei nomi XML)

Importa i prefissi degli spazi dei nomi XML da utilizzare nei valori letterali XML e nelle proprietà Axis XML.

## <a name="syntax"></a>Sintassi

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>Parti

`xmlNamespacePrefix`  
Facoltativa. Stringa a cui possono fare riferimento gli elementi e gli attributi XML `xmlNamespaceName` . Se non `xmlNamespacePrefix` viene specificato alcun oggetto, lo spazio dei nomi XML importato sarà lo spazio dei nomi XML predefinito. Deve essere un identificatore XML valido. Per ulteriori informazioni, vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).

`xmlNamespaceName`  
Obbligatorio. Stringa che identifica lo spazio dei nomi XML importato.

## <a name="remarks"></a>Commenti

È possibile utilizzare l' `Imports` istruzione per definire gli spazi dei nomi XML globali che è possibile utilizzare con i valori letterali XML e le proprietà Axis XML o come parametri passati all' `GetXmlNamespace` operatore. Per informazioni sull'uso dell' `Imports` istruzione per importare un alias che può essere usato in presenza di nomi di tipo nel codice, vedere [istruzione Imports (tipo e spazio dei nomi .NET)](imports-statement-net-namespace-and-type.md). La sintassi per la dichiarazione di uno spazio dei nomi XML tramite l' `Imports` istruzione è identica a quella utilizzata in XML. Pertanto, è possibile copiare una dichiarazione dello spazio dei nomi da un file XML e utilizzarla in un' `Imports` istruzione.

I prefissi degli spazi dei nomi XML sono utili quando si desidera creare ripetutamente elementi XML che appartengono allo stesso spazio dei nomi. Il prefisso dello spazio dei nomi XML dichiarato con l' `Imports` istruzione è globale nel senso che è disponibile per tutto il codice del file. È possibile usarlo quando si creano valori letterali dell'elemento XML e quando si accede alle proprietà Axis XML. Per altre informazioni, vedere [valore letterale elemento XML](../xml-literals/xml-element-literal.md) e [Proprietà Axis XML](../xml-axis/index.md).

Se si definisce uno spazio dei nomi XML globale senza un prefisso dello spazio dei nomi (ad esempio,), lo spazio dei nomi `Imports <xmlns="http://SomeNameSpace>"` viene considerato lo spazio dei nomi XML predefinito. Lo spazio dei nomi XML predefinito viene utilizzato per qualsiasi valore letterale elemento XML o proprietà asse degli attributi XML che non specificano in modo esplicito uno spazio dei nomi. Lo spazio dei nomi predefinito viene utilizzato anche se lo spazio dei nomi specificato è lo spazio dei nomi vuoto (ovvero `xmlns=""` ). Lo spazio dei nomi XML predefinito non si applica agli attributi XML nei valori letterali XML o alle proprietà axis dell'attributo XML che non dispongono di uno spazio dei nomi.

Gli spazi dei nomi XML definiti in un valore letterale XML, denominati *spazi dei nomi XML locali*, hanno la precedenza sugli spazi dei nomi XML definiti dall' `Imports` istruzione come globali. Gli spazi dei nomi XML definiti dall' `Imports` istruzione hanno la precedenza sugli spazi dei nomi XML importati per un progetto Visual Basic. Se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi locale non si applica alle espressioni incorporate.

Gli spazi dei nomi XML globali seguono le stesse regole di definizione e definizione dell'ambito di .NET Framework spazi dei nomi. Di conseguenza, è possibile includere un' `Imports` istruzione per definire uno spazio dei nomi XML globale ovunque sia possibile importare uno spazio dei nomi .NET Framework. Sono inclusi i file di codice e gli spazi dei nomi importati a livello di progetto. Per informazioni sugli spazi dei nomi importati a livello di progetto, vedere [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).

Ogni file di origine può contenere un numero qualsiasi di `Imports` istruzioni. Devono seguire le dichiarazioni di opzioni, ad esempio l' `Option Strict` istruzione, e devono precedere le dichiarazioni degli elementi di programmazione, ad esempio le `Module` `Class` istruzioni o.

## <a name="example"></a>Esempio

Nell'esempio seguente viene importato uno spazio dei nomi XML predefinito e uno spazio dei nomi XML identificato con il prefisso `ns` . Viene quindi creato un valore letterale XML che utilizza entrambi gli spazi dei nomi.

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

Questo codice visualizza il testo seguente:

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a>Esempio

Nell'esempio seguente viene importato il prefisso dello spazio dei nomi XML `ns` . Viene quindi creato un valore letterale XML che utilizza il prefisso dello spazio dei nomi e viene visualizzato il formato finale dell'elemento.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

Questo codice visualizza il testo seguente:

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

Si noti che il compilatore ha convertito il prefisso dello spazio dei nomi XML da un prefisso globale a una definizione di prefisso locale.

## <a name="example"></a>Esempio

Nell'esempio seguente viene importato il prefisso dello spazio dei nomi XML `ns` . Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

Questo codice visualizza il testo seguente:

`Patrick Hines`

## <a name="see-also"></a>Vedere anche

- [Valore letterale di elemento XML](../xml-literals/xml-element-literal.md)
- [Proprietà Axis XML](../xml-axis/index.md)
- [Nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Operatore GetXmlNamespace](../operators/getxmlnamespace-operator.md)
