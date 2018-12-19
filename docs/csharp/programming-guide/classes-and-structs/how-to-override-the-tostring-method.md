---
title: "Procedura: Eseguire l'override del metodo ToString - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 0be35b64e9df3ec2a78c62735b1b7072e092f073
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240736"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Procedura: Eseguire l'override del metodo ToString (Guida per programmatori C#)
Ogni classe o struct in C# eredita in modo implicito la classe <xref:System.Object>. Ogni oggetto in C# ottiene quindi il metodo <xref:System.Object.ToString%2A>, che restituisce una rappresentazione di stringa dell'oggetto. Ad esempio, tutte le variabili di tipo `int` hanno un metodo `ToString` che consente loro di restituire il rispettivo contenuto sotto forma di stringa:  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 Quando si crea una classe o uno struct personalizzato, eseguire l'override del metodo <xref:System.Object.ToString%2A> per fornire informazioni sul tipo al codice client.  
  
 Per informazioni sull'uso di stringhe di formato e altri tipi di formattazione personalizzata con il metodo `ToString`, vedere [Formattazione di tipi](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
>  Dopo aver deciso quali informazioni comunicare tramite questo metodo, considerare se la classe o lo struct sarà usato da codice non attendibile. Verificare attentamente di non indicare informazioni che potrebbero essere sfruttate da malware.  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a>Per eseguire l'override del metodo ToString nella classe o nello struct  
  
1.  Dichiarare un metodo `ToString` con i modificatori e il tipo restituito seguenti:  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  Implementare il metodo in modo che restituisca una stringa.  
  
     L'esempio seguente restituisce il nome della classe oltre ai dati specifici per una particolare istanza della classe.  
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     È anche possibile testare il metodo `ToString` come illustrato nel codice di esempio seguente:  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IFormattable>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Stringhe](../../../csharp/programming-guide/strings/index.md)  
- [string](../../../csharp/language-reference/keywords/string.md)  
- [new](../../../csharp/language-reference/keywords/new.md)  
- [override](../../../csharp/language-reference/keywords/override.md)  
- [virtual](../../../csharp/language-reference/keywords/virtual.md)  
- [Formattazione di tipi](../../../standard/base-types/formatting-types.md)
