---
title: Elaborazione del file XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 4230fd88b4b60c631135f5b7fb15f4b6272b5351
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347295"
---
# <a name="processing-the-xml-file-visual-basic"></a>Elaborazione del file XML (Visual Basic)
Il compilatore genera una stringa identificativa (ID) per ciascun costrutto del codice che contiene tag per la creazione della documentazione. (For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md).) The ID string uniquely identifies the construct. Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item.  
  
 The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.  
  
 Per generare gli ID, il compilatore applica le regole seguenti:  
  
- Assenza di spazi vuoti nella stringa.  
  
- La prima parte della stringa ID specifica il tipo di membro, con un singolo carattere seguito dai due punti. The following member types are used.  
  
|Carattere|Descrizione|  
|---|---|  
|N|namespace<br /><br /> You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.|  
|T|type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|field: `Dim`|  
|P|property: `Property` (including default properties)|  
|M|method: `Sub`, `Function`, `Declare`, `Operator`|  
|E|event: `Event`|  
|!|stringa di errore<br /><br /> Nella parte restante della stringa vengono fornite informazioni sull'errore. The Visual Basic compiler generates error information for links that cannot be resolved.|  
  
- The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace. The name of the item, its enclosing type(s), and the namespace are separated by periods. If the name of the item itself contains periods, they are replaced by the number sign (#). It is assumed that no item has a number sign directly in its name. For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.  
  
- Per le proprietà e i metodi, se il metodo ha degli argomenti, verrà incluso di seguito l'elenco degli argomenti racchiuso tra parentesi. Se non sono presenti argomenti, non verranno usate le parentesi. Gli argomenti sono separati da virgole. The encoding of each argument follows directly how it is encoded in a .NET Framework signature.  
  
## <a name="example"></a>Esempio  
 The following code shows how the ID strings for a class and its members are generated.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
