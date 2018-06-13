---
title: Istruzione Imports (spazio dei nomi XML)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: ba7475416d8a4e2eb3c892d457c03eeb695045eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604562"
---
# <a name="imports-statement-xml-namespace"></a>Istruzione Imports (spazio dei nomi XML)
Importa i prefissi dello spazio dei nomi XML per l'utilizzo in valori letterali XML e proprietà axis XML.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Parti  
 `xmlNamespacePrefix`  
 Facoltativo. La stringa da cui XML elementi e attributi possono fare riferimento a `xmlNamespaceName`. Se non `xmlNamespacePrefix` viene fornito, spazio dei nomi XML importato è lo spazio dei nomi XML predefinito. Deve essere un identificatore XML valido. Per ulteriori informazioni, vedere [attributi e i nomi di elementi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Obbligatorio. Stringa che identifica lo spazio dei nomi XML importato.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare il `Imports` istruzione per definire spazi dei nomi XML globali che è possibile utilizzare con i valori letterali XML e proprietà axis XML o come parametri per il `GetXmlNamespace` operatore. (Per informazioni sull'utilizzo di `Imports` per importare un alias che può essere usato in cui vengono utilizzati i nomi dei tipi nel codice, vedere [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) La sintassi per dichiarare uno spazio dei nomi XML utilizzando il `Imports` istruzione è identica a quella utilizzata nel codice XML. Pertanto, è possibile copiare una dichiarazione dello spazio dei nomi da un file XML e utilizzarla in un `Imports` istruzione.  
  
 Prefissi di spazio dei nomi XML sono utili quando si desidera creare ripetutamente elementi XML che provengono dallo stesso spazio dei nomi. Il prefisso dello spazio dei nomi XML dichiarati con la `Imports` è globale nel senso che sia disponibile a tutto il codice nel file di istruzione. È possibile utilizzarlo quando si creano valori letterali dell'elemento XML e quando si accede a proprietà axis XML. Per ulteriori informazioni, vedere [XML elemento Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e [proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Se si definisce un spazio dei nomi XML globale senza un prefisso dello spazio dei nomi (ad esempio, `Imports <xmlns="http://SomeNameSpace>"`), tale spazio dei nomi viene considerato lo spazio dei nomi XML predefinito. Spazio dei nomi XML predefinito viene utilizzato per le proprietà axis XML attributo che non specificano in modo esplicito uno spazio dei nomi o valori letterali dell'elemento XML. Spazio dei nomi predefinito viene usato anche se lo spazio dei nomi specificato è lo spazio dei nomi vuoto (vale a dire `xmlns=""`). Spazio dei nomi XML predefinito non è applicabile ad attributi XML nei valori letterali XML o per le proprietà axis dell'attributo XML non dispone di uno spazio dei nomi.  
  
 Spazi dei nomi XML definiti in un valore letterale XML, che vengono chiamati *locale spazi dei nomi XML*, hanno la precedenza su spazi dei nomi XML definiti per il `Imports` istruzione come globale. Spazi dei nomi XML definiti per il `Imports` istruzione hanno la precedenza su spazi dei nomi XML importato per un progetto Visual Basic. Se un valore letterale XML definisce uno spazio dei nomi XML, spazio dei nomi locale non è applicabile per le espressioni incorporate.  
  
 Spazi dei nomi XML globale seguire le stesse regole di ambito e di definizione degli spazi dei nomi .NET Framework. Di conseguenza, è possibile includere un `Imports` istruzione per definire un spazio dei nomi XML globale ovunque sia possibile importare uno spazio dei nomi .NET Framework. Questo include i file di codice e spazi dei nomi importati a livello di progetto. Per informazioni sugli spazi dei nomi importato a livello di progetto, vedere [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Ogni file di origine può contenere un numero qualsiasi di `Imports` istruzioni. Queste devono seguire le dichiarazioni di opzione, ad esempio il `Option Strict` istruzione essi devono precedere dichiarazione di elemento di programmazione, ad esempio `Module` o `Class` istruzioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente importa uno spazio dei nomi XML predefinito e un spazio dei nomi XML identificato con il prefisso `ns`. Crea quindi i valori letterali XML che utilizzano entrambi gli spazi dei nomi.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
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
 L'esempio seguente importa il prefisso dello spazio dei nomi XML `ns`. Crea quindi un valore letterale XML che viene utilizzato il prefisso dello spazio dei nomi e visualizza il formato dell'elemento finale.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Si noti che il compilatore converte il prefisso dello spazio dei nomi XML da un prefisso globale a una definizione del prefisso locale.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente importa il prefisso dello spazio dei nomi XML `ns`. Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche  
 [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [Operatore GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
