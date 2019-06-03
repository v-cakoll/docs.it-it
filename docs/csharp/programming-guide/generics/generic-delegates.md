---
title: Delegati generici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: ff19b3d71858552158a8ae5d0ab362a86dc98e65
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423500"
---
# <a name="generic-delegates-c-programming-guide"></a>Delegati generici (Guida per programmatori C#)
Un [delegato](../../../csharp/language-reference/keywords/delegate.md) può definire i propri parametri di tipo. Il codice che fa riferimento al delegato generico può specificare l'argomento tipo per creare un tipo costruito chiuso, proprio come per la creazione di un'istanza di una classe generica o la chiamata di un metodo generico, come mostrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 C# versione 2.0 include una nuova funzionalità chiamata conversione di gruppi di metodi, applicabile a tipi delegato sia concreti sia generici, e che permette di scrivere la riga precedente con questa sintassi semplificata:  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 I delegati definiti in una classe generica possono usare parametri di tipo di classe generica allo stesso modo dei metodi della classe.  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 Il codice che fa riferimento al delegato deve specificare l'argomento tipo della classe che lo contiene, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 I delegati generici sono particolarmente utili per definire eventi basati sul normale schema progettuale, perché l'argomento sender può essere fortemente tipizzato e non è più necessario eseguirne il cast a e da <xref:System.Object>.  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Introduzione ai generics](../../../csharp/programming-guide/generics/index.md)
- [Metodi generici](../../../csharp/programming-guide/generics/generic-methods.md)
- [Classi generiche](../../../csharp/programming-guide/generics/generic-classes.md)
- [Interfacce generiche](../../../csharp/programming-guide/generics/generic-interfaces.md)
- [Delegati](../../../csharp/programming-guide/delegates/index.md)
- [Generics](~/docs/standard/generics/index.md)
