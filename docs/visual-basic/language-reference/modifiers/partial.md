---
title: Partial
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: 650ead2f0deb9813b26241a6a4676907de3f263d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362242"
---
# <a name="partial-visual-basic"></a>Partial (Visual Basic)
Indica che una dichiarazione di tipo è una definizione parziale del tipo.  
  
 Si può dividere la definizione di un tipo tra più dichiarazioni mediante la parola chiave `Partial`. Si può usare il numero di dichiarazioni parziali desiderato, in un numero qualsiasi di file di origine differenti.  Tutte le dichiarazioni, tuttavia, devono trovarsi nello stesso assembly e nello stesso spazio dei nomi.  
  
> [!NOTE]
> Visual Basic supporta i *metodi parziali*, che in genere sono implementati nelle classi parziali. Per altre informazioni, vedere [metodi parziali](../../programming-guide/language-features/procedures/partial-methods.md) e [istruzione secondaria](../statements/sub-statement.md).  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attrlist`|Facoltativa. Elenco degli attributi applicabili al tipo. È necessario racchiudere l' [elenco degli attributi](../statements/attribute-list.md) tra parentesi angolari ( `< >` ).|  
|`accessmodifier`|Facoltativa. Specifica il tipo di codice che può accedere al tipo. Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativa. Vedere [Shadows](shadows.md).|  
|`MustInherit`|Facoltativa. Vedere [MustInherit](mustinherit.md).|  
|`NotInheritable`|Facoltativa. Vedere [NotInheritable](notinheritable.md).|  
|`name`|Obbligatorio. Nome del tipo. Deve corrispondere al nome definito in tutte le altre dichiarazioni parziali dello stesso tipo.|  
|`Of`|Facoltativa. Specifica che si tratta di un tipo generico. Vedere [tipi generici in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Obbligatorio se [si usa.](../statements/of-clause.md) Vedere [elenco dei tipi](../statements/type-list.md).|  
|`Inherits`|Facoltativa. Vedere [istruzione Inherits](../statements/inherits-statement.md).|  
|`classname`|Obbligatorio se si usa `Inherits`. Nome della classe o dell'interfaccia da cui deriva la classe.|  
|`Implements`|Facoltativa. Vedere [istruzione Implements](../statements/implements-statement.md).|  
|`interfacenames`|Obbligatorio se si usa `Implements`. Nomi delle interfacce implementate dal tipo.|  
|`variabledeclarations`|Facoltativa. Istruzioni che dichiarano variabili ed eventi aggiuntivi per il tipo.|  
|`proceduredeclarations`|Facoltativa. Istruzioni che dichiarano e definiscono routine aggiuntive per il tipo.|  
|`End Class` o `End Structure`|Termina questa definizione `Class` o `Structure` parziale.|  
  
## <a name="remarks"></a>Commenti  
 Visual Basic usa definizioni di classi parziali per separare il codice generato dal codice creato dall'utente in file di origine distinti. Ad esempio, **Progettazione Windows Form** definisce classi parziali per controlli come <xref:System.Windows.Forms.Form>. In questi controlli il codice generato non deve essere modificato.  
  
 Durante la creazione di un tipo parziale vengono applicate tutte le regole per la creazione delle classi, delle strutture, delle interfacce e dei moduli, ad esempio quelle relative all'uso dei modificatori e all'ereditarietà.  
  
## <a name="best-practices"></a>Procedure consigliate  
  
- In condizioni normali, non è consigliabile suddividere lo sviluppo di un singolo tipo in due o più dichiarazioni. Pertanto, nella maggior parte dei casi non occorre specificare la parola chiave `Partial`.  
  
- Per migliorare la leggibilità, ogni dichiarazione parziale di un tipo deve includere la parola chiave `Partial`. Il compilatore consente che la parola chiave venga omessa al massimo in una dichiarazione parziale. Se viene omessa in due o più dichiarazioni, viene segnalato un errore.  
  
## <a name="behavior"></a>Comportamento  
  
- **Unione delle dichiarazioni** Il compilatore considera il tipo come l'unione di tutte le relative dichiarazioni parziali. Ogni modificatore di ciascuna definizione parziale si applica all'intero tipo e ogni membro di ciascuna definizione parziale è disponibile per l'intero tipo.  
  
- **Promozione tipo non consentita per i tipi parziali nei moduli.** Se una definizione parziale si trova all'interno di un modulo, l'effetto della promozione tipo di tale tipo viene automaticamente annullato. In questo caso, un set di definizioni parziali può generare risultati imprevisti e persino errori del compilatore. Per ulteriori informazioni, vedere [promozione del tipo](../../programming-guide/language-features/declared-elements/type-promotion.md).  
  
     Il compilatore unisce le definizioni parziali solo se i relativi percorsi completi sono identici.  
  
 È possibile usare la parola chiave `Partial` nei contesti seguenti:  
  
 [Istruzione Class](../statements/class-statement.md)  
  
 [Istruzione Structure](../statements/structure-statement.md)  
  
## <a name="example"></a>Esempio  
 L'esempio seguente suddivide la definizione della classe `sampleClass` in due dichiarazioni, ognuna delle quali definisce una routine `Sub` differente.  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 Le due definizioni parziali nell'esempio precedente possono trovarsi nello stesso file di origine o in due file di origine differenti.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Class](../statements/class-statement.md)
- [Istruzione Structure](../statements/structure-statement.md)
- [Promozione tipo](../../programming-guide/language-features/declared-elements/type-promotion.md)
- [Shadows](shadows.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Metodi parziali](../../programming-guide/language-features/procedures/partial-methods.md)
