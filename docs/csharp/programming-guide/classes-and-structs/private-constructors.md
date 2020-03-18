---
title: Costruttori privati - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 2f8b93fbeb7c2996f3e2683fe86f159fbfa61a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705444"
---
# <a name="private-constructors-c-programming-guide"></a>Costruttori privati (Guida per programmatori C#)
Un costruttore privato è un costruttore di istanza speciale. Viene generalmente usato in classi contenenti solo membri statici. Se una classe ha uno o più costruttori privati ma non include alcun costruttore pubblico, le altre classi, ad eccezione di quelle annidate, non potranno creare istanze della classe. Ad esempio:  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 La dichiarazione del costruttore vuoto impedisce la generazione automatica di un costruttore senza parametri. Tenere presente che se non si usa un modificatore di accesso con il costruttore, questo rimarrà di tipo privato per impostazione predefinita. Tuttavia, il modificatore [private](../../language-reference/keywords/private.md) viene solitamente usato in modo esplicito per specificare che non è possibile creare un'istanza della classe.  
  
 I costruttori privati vengono usati per impedire la creazione di istanze di una classe in assenza di metodi e campi di istanza, ad esempio la classe <xref:System.Math>, oppure quando viene chiamato un metodo per ottenere un'istanza di una classe. Se tutti i metodi della classe sono statici, è consigliabile rendere statica l'intera classe. Per altre informazioni, vedere [Classi statiche e membri di classi statiche](./static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato l'esempio di una classe che usa un costruttore privato.  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 Se si rimuove il commento dall'istruzione dell'esempio riportata di seguito, verrà generato un errore poiché non è possibile accedere al costruttore a causa del livello di protezione:  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Operatore as](~/_csharplang/spec/classes.md#private-constructors) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Costruttori](./constructors.md)
- [Finalizzatori](./destructors.md)
- [Privato](../../language-reference/keywords/private.md)
- [pubblico](../../language-reference/keywords/public.md)
