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
ms.openlocfilehash: 5d88a01f90bc91a88229d19aa2368f8c71075b2f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404499"
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
|`basetypenames`|Obbligatorio. Nome della classe da cui deriva questa classe.<br /><br /> -oppure-<br /><br /> Nomi delle interfacce da cui deriva questa interfaccia. Utilizzare le virgole per separare più nomi.|  
  
## <a name="remarks"></a>Commenti  
 Se utilizzata, l' `Inherits` istruzione deve essere la prima riga non vuota non di commento in una definizione di classe o di interfaccia. Deve seguire immediatamente l' `Class` istruzione o `Interface` .  
  
 È possibile utilizzare `Inherits` solo in una classe o in un'interfaccia. Ciò significa che il contesto di dichiarazione per un'ereditarietà non può essere un file di origine, uno spazio dei nomi, una struttura, un modulo, una procedura o un blocco.  
  
## <a name="rules"></a>Regole  
  
- **Ereditarietà della classe.** Se una classe utilizza l' `Inherits` istruzione, è possibile specificare una sola classe di base.  
  
     Una classe non può ereditare da una classe annidata al suo interno.  
  
- **Ereditarietà dell'interfaccia.** Se un'interfaccia usa l' `Inherits` istruzione, è possibile specificare una o più interfacce di base. È possibile ereditare da due interfacce anche se ognuna definisce un membro con lo stesso nome. In tal caso, il codice di implementazione deve usare la qualificazione del nome per specificare il membro che sta implementando.  
  
     Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo. Un'interfaccia, ad esempio, `Public` non può ereditare da un' `Friend` interfaccia.  
  
     Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.  
  
 Un esempio di ereditarietà della classe nel .NET Framework è la <xref:System.ArgumentException> classe, che eredita dalla <xref:System.SystemException> classe. In questo modo vengono fornite <xref:System.ArgumentException> tutte le proprietà e le procedure predefinite richieste dalle eccezioni di sistema, ad esempio la <xref:System.Exception.Message%2A> proprietà e il <xref:System.Exception.ToString%2A> metodo.  
  
 Un esempio di ereditarietà dell'interfaccia nel .NET Framework è l' <xref:System.Collections.ICollection> interfaccia, che eredita dall' <xref:System.Collections.IEnumerable> interfaccia. Questo fa <xref:System.Collections.ICollection> in modo che erediti la definizione dell'enumeratore necessario per attraversare una raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `Inherits` istruzione per mostrare in che modo una classe denominata `thisClass` può ereditare tutti i membri di una classe di base denominata `anotherClass` .  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'ereditarietà di più interfacce.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 L'interfaccia denominata `thisInterface` include ora tutte le definizioni nelle <xref:System.IComparable> interfacce, <xref:System.IDisposable> e, che <xref:System.IFormattable> i membri ereditati forniscono rispettivamente per il confronto specifico del tipo di due oggetti, il rilascio delle risorse allocate e l'espressione del valore di un oggetto come `String` . Una classe che implementa `thisInterface` deve implementare tutti i membri di ogni interfaccia di base.  
  
## <a name="see-also"></a>Vedere anche

- [MustInherit](../modifiers/mustinherit.md)
- [NotInheritable](../modifiers/notinheritable.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
- [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Interfacce](../../programming-guide/language-features/interfaces/index.md)
