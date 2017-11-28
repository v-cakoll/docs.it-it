---
title: "Proprietà Value XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c52ac09e209d6e3f0cfd877a071cbbe3ab96f18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-value-property-visual-basic"></a>Proprietà Value XML (Visual Basic)
Fornisce l'accesso al valore del primo elemento di una raccolta di <xref:System.Xml.Linq.XElement> oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
object.Value  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`object`|Obbligatorio. Raccolta di oggetti <xref:System.Xml.Linq.XElement>.|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto `String` che contiene il valore del primo elemento della raccolta, o `Nothing` se la raccolta è vuota.  
  
## <a name="remarks"></a>Note  
 Il <xref:System.Xml.Linq.XElement.Value%2A> proprietà rende più semplice accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. Questa proprietà controlla innanzitutto se la raccolta contiene almeno un oggetto. Se la raccolta è vuota, questa proprietà restituisce `Nothing`. In caso contrario, questa proprietà restituisce il valore di <xref:System.Xml.Linq.XElement.Value%2A> proprietà del primo elemento nella raccolta.  
  
> [!NOTE]
>  Quando si accede al valore di un attributo XML utilizzando il ' @' identificatore, il valore dell'attributo viene restituito come un `String` e non è necessario specificare in modo esplicito il <xref:System.Xml.Linq.XAttribute.Value%2A> proprietà.  
  
 Per accedere agli altri elementi in una raccolta, è possibile utilizzare la proprietà dell'indicizzatore di estensione XML. Per ulteriori informazioni, vedere [proprietà dell'indicizzatore di estensione](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## <a name="inheritance"></a>Ereditarietà  
 La maggior parte degli utenti non dovrà implementare <xref:System.Collections.Generic.IEnumerable%601>ed è pertanto possibile ignorare questa sezione.  
  
 Il <xref:System.Xml.Linq.XElement.Value%2A> proprietà è una proprietà di estensione per tipi che implementano `IEnumerable(Of XElement)`. L'associazione di questa proprietà di estensione è simile all'associazione di metodi di estensione: se un tipo implementa una delle interfacce e definisce una proprietà con il nome "Value", tale proprietà ha la precedenza sulla proprietà di estensione. In altre parole, questo <xref:System.Xml.Linq.XElement.Value%2A> può eseguire l'override di proprietà mediante la definizione di una nuova proprietà in una classe che implementa `IEnumerable(Of XElement)`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Xml.Linq.XElement.Value%2A> proprietà per accedere al primo nodo in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. Nell'esempio viene utilizzata la proprietà di asse figlio per ottenere la raccolta di tutti i nodi figlio denominati `phone` che si trovano i `contact` oggetto.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere il valore di un attributo XML da una raccolta di <xref:System.Xml.Linq.XAttribute> oggetti. Nell'esempio viene utilizzata la proprietà axis dell'attributo per visualizzare il valore del `type` attributo per tutti gli il `phone` elementi.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [Proprietà dell'indicizzatore di estensione](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [Proprietà Child Axis XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [Proprietà axis dell'attributo XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
