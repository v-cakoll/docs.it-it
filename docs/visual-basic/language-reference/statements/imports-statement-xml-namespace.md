---
title: Imports (istruzione) - Namespace XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 97d08113a37477add9d770b0a680c303fe7e3040
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841407"
---
# <a name="imports-statement-xml-namespace"></a>Istruzione Imports (spazio dei nomi XML)
Importa i prefissi dello spazio dei nomi XML per l'utilizzo in valori letterali XML e proprietà axis XML.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Parti  
 `xmlNamespacePrefix`  
 Facoltativo. La stringa da cui XML gli elementi e attributi farvi riferimento `xmlNamespaceName`. Se nessun `xmlNamespacePrefix` viene fornito, lo spazio dei nomi XML importato è lo spazio dei nomi XML predefinito. Deve essere un identificatore XML valido. Per altre informazioni, vedere [attributi e i nomi di elementi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Obbligatorio. Stringa che identifica lo spazio dei nomi XML da importare.  
  
## <a name="remarks"></a>Note  
 È possibile usare la `Imports` istruzione per definire spazi dei nomi XML globale che è possibile usare con i valori letterali XML e proprietà axis XML o come parametri passati al `GetXmlNamespace` operatore. (Per informazioni sull'uso di `Imports` per importare un alias che può essere utilizzato in cui vengono usati i nomi dei tipi nel codice, vedere [istruzione Imports (tipo e .NET Namespace)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) La sintassi per dichiarare uno spazio dei nomi XML usando la `Imports` istruzione è identica a quella usata nel codice XML. Pertanto, è possibile copiare una dichiarazione dello spazio dei nomi da un file XML e usarla in un `Imports` istruzione.  
  
 I prefissi dello spazio dei nomi XML sono utili quando si desidera creare ripetutamente gli elementi XML che provengono dallo stesso spazio dei nomi. Il prefisso dello spazio dei nomi XML dichiarati con la `Imports` istruzione è globale nel senso che sia disponibile per tutto il codice nel file. È possibile utilizzarlo quando si creano valori letterali dell'elemento XML e quando si accede proprietà axis XML. Per altre informazioni, vedere [letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e [proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md).  
  
 Se si definisce uno spazio dei nomi XML globale senza un prefisso dello spazio dei nomi (ad esempio, `Imports <xmlns="http://SomeNameSpace>"`), tale spazio dei nomi viene considerato lo spazio dei nomi XML predefinito. Lo spazio dei nomi XML predefinito viene usato per qualsiasi valori letterali dell'elemento XML o una proprietà di asse attributo XML che non specificano in modo esplicito uno spazio dei nomi. Spazio dei nomi predefinito viene usato anche se lo spazio dei nomi specificato è lo spazio dei nomi vuoto (vale a dire `xmlns=""`). Lo spazio dei nomi XML predefinito non è applicabile agli attributi XML nei valori letterali XML o di proprietà dell'asse degli attributi XML che non hanno uno spazio dei nomi.  
  
 Spazi dei nomi XML definiti in un valore letterale XML, che vengono chiamati *spazi dei nomi XML locale*, hanno la precedenza su spazi dei nomi XML definiti dal `Imports` istruzione come globali. Spazi dei nomi XML definiti dal `Imports` istruzione hanno la precedenza su spazi dei nomi XML importato per un progetto Visual Basic. Se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi locale non è applicabile per le espressioni incorporate.  
  
 Spazi dei nomi XML globale seguono le stesse regole di ambito e la definizione degli spazi dei nomi .NET Framework. Di conseguenza, è possibile includere un `Imports` istruzione per definire uno spazio dei nomi XML globale ovunque sia possibile importare uno spazio dei nomi .NET Framework. Sono inclusi sia i file di codice e gli spazi dei nomi importato a livello di progetto. Per informazioni sugli spazi dei nomi importato a livello di progetto, vedere [riferimenti (pagina), creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Ogni file di origine può contenere un numero qualsiasi di `Imports` istruzioni. Questi devono seguire le dichiarazioni di opzione, ad esempio la `Option Strict` istruzione che deve precedere dichiarazione di elemento di programmazione, ad esempio `Module` o `Class` istruzioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente importa uno spazio dei nomi XML predefinito e uno spazio dei nomi XML identificato con il prefisso `ns`. Crea quindi i valori letterali XML che utilizzano entrambi gli spazi dei nomi.  
  
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
 L'esempio seguente importa il prefisso dello spazio dei nomi XML `ns`. Crea quindi un valore letterale XML che usa il prefisso dello spazio dei nomi e visualizza il formato dell'elemento finale.  
  
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
  
 Si noti che il compilatore converte il prefisso dello spazio dei nomi XML da un prefisso globale alla definizione di un prefisso locale.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente importa il prefisso dello spazio dei nomi XML `ns`. Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche

- [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Operatore GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
