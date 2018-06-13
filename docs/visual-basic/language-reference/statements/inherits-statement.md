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
ms.openlocfilehash: 43a8aa4e9e04ee035cb52e9f829de13e5c022217
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604341"
---
# <a name="inherits-statement"></a>Inherits Statement
Fa sì che la classe corrente o l'interfaccia da cui ereditare attributi, le variabili, proprietà, procedure e gli eventi di un'altra classe o un set di interfacce.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`basetypenames`|Obbligatorio. Il nome della classe da cui deriva questa classe.<br /><br /> oppure<br /><br /> I nomi delle interfacce da cui deriva questa interfaccia. Utilizzare le virgole per separare più nomi.|  
  
## <a name="remarks"></a>Note  
 Se utilizzato, il `Inherits` istruzione deve essere la prima riga non vuota e non di commento in una definizione di classe o interfaccia. Deve seguire immediatamente la `Class` o `Interface` istruzione.  
  
 È possibile utilizzare `Inherits` solo in una classe o interfaccia. Ciò significa che il contesto della dichiarazione di un'ereditarietà non può essere un file di origine, lo spazio dei nomi, struttura, modulo, routine o blocco.  
  
## <a name="rules"></a>Regole  
  
-   **Ereditarietà della classe.** Se una classe utilizza il `Inherits` istruzione, è possibile specificare solo una classe base.  
  
     Una classe non può ereditare da una classe annidata al suo interno.  
  
-   **Ereditarietà dell'interfaccia.** Se un'interfaccia viene utilizzata la `Inherits` istruzione, è possibile specificare uno o più interfacce di base. È possibile ereditare da due interfacce, anche se ciascuna di esse definisce un membro con lo stesso nome. Se si esegue questa operazione, il codice di implementazione deve utilizzare la qualificazione di nomi per specificare quale membro che sta implementando.  
  
     Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo. Ad esempio, un `Public` interfaccia non può ereditare da un `Friend` interfaccia.  
  
     Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.  
  
 Un esempio di ereditarietà delle classi in .NET Framework è la <xref:System.ArgumentException> (classe), che eredita dalla <xref:System.SystemException> classe. Viene fornita al <xref:System.ArgumentException> tutte le proprietà predefinite le procedure necessarie per le eccezioni di sistema, ad esempio il <xref:System.Exception.Message%2A> proprietà e <xref:System.Exception.ToString%2A> metodo.  
  
 Un esempio di ereditarietà dell'interfaccia in .NET Framework è la <xref:System.Collections.ICollection> interfaccia che eredita dal <xref:System.Collections.IEnumerable> interfaccia. In questo modo <xref:System.Collections.ICollection> eredita la definizione dell'enumeratore richiesto per scorrere una raccolta.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Inherits` istruzione per mostrare come una classe denominata `thisClass` può ereditare tutti i membri di una classe base denominata `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra l'ereditarietà di più interfacce.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 L'interfaccia denominata `thisInterface` ora include tutte le definizioni di <xref:System.IComparable>, <xref:System.IDisposable>, e <xref:System.IFormattable> interfacce dei membri ereditati forniscono rispettivamente per il confronto di tipo specifico di due oggetti, come rilasciare le risorse allocate e il valore di un oggetto come esprimere una `String`. Una classe che implementa `thisInterface` deve implementare ogni membro di ogni interfaccia di base.  
  
## <a name="see-also"></a>Vedere anche  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
