---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 6e6e9cc9210232059210862f2bda691c57b372d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353231"
---
# <a name="inherits-statement"></a>Inherits Statement
Fa in modo che la classe o l'interfaccia corrente erediti gli attributi, le variabili, le proprietà, le procedure e gli eventi da un'altra classe o set di interfacce.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`basetypenames`|Obbligatoria. Nome della classe da cui deriva questa classe.<br /><br /> -oppure-<br /><br /> Nomi delle interfacce da cui deriva questa interfaccia. Utilizzare le virgole per separare più nomi.|  
  
## <a name="remarks"></a>Note  
 Se utilizzata, l'istruzione `Inherits` deve essere la prima riga non vuota non di commento in una definizione di classe o di interfaccia. Deve seguire immediatamente l'istruzione `Class` o `Interface`.  
  
 È possibile utilizzare `Inherits` solo in una classe o in un'interfaccia. Ciò significa che il contesto di dichiarazione per un'ereditarietà non può essere un file di origine, uno spazio dei nomi, una struttura, un modulo, una procedura o un blocco.  
  
## <a name="rules"></a>Regole  
  
- **Ereditarietà della classe.** Se una classe utilizza l'istruzione `Inherits`, è possibile specificare una sola classe di base.  
  
     Una classe non può ereditare da una classe annidata al suo interno.  
  
- **Ereditarietà dell'interfaccia.** Se un'interfaccia usa l'istruzione `Inherits`, è possibile specificare una o più interfacce di base. È possibile ereditare da due interfacce anche se ognuna definisce un membro con lo stesso nome. In tal caso, il codice di implementazione deve usare la qualificazione del nome per specificare il membro che sta implementando.  
  
     Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo. Ad esempio, un'interfaccia `Public` non può ereditare da un'interfaccia `Friend`.  
  
     Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.  
  
 Un esempio di ereditarietà della classe nel .NET Framework è la classe <xref:System.ArgumentException>, che eredita dalla classe <xref:System.SystemException>. Ciò consente di <xref:System.ArgumentException> tutte le proprietà e le procedure predefinite richieste dalle eccezioni di sistema, ad esempio la proprietà <xref:System.Exception.Message%2A> e il metodo <xref:System.Exception.ToString%2A>.  
  
 Un esempio di ereditarietà dell'interfaccia nel .NET Framework è l'interfaccia <xref:System.Collections.ICollection>, che eredita dall'interfaccia <xref:System.Collections.IEnumerable>. Questo fa sì che <xref:System.Collections.ICollection> erediti la definizione dell'enumeratore necessario per attraversare una raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `Inherits` per mostrare in che modo una classe denominata `thisClass` può ereditare tutti i membri di una classe di base denominata `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'ereditarietà di più interfacce.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 L'interfaccia denominata `thisInterface` include ora tutte le definizioni nelle interfacce <xref:System.IComparable>, <xref:System.IDisposable>e <xref:System.IFormattable> i membri ereditati forniscono rispettivamente per il confronto specifico del tipo di due oggetti, il rilascio delle risorse allocate e l'espressione del valore di un oggetto come `String`. Una classe che implementa `thisInterface` deve implementare tutti i membri di ogni interfaccia di base.  
  
## <a name="see-also"></a>Vedere anche

- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
