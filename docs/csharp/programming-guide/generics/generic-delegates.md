---
title: Delegati generici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 3c6f29ead76f2e835d78a15d782e1aaca28942c8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423272"
---
# <a name="generic-delegates-c-programming-guide"></a>Delegati generici (Guida per programmatori C#)
Un [delegato](../../language-reference/builtin-types/reference-types.md) può definire i propri parametri di tipo. Il codice che fa riferimento al delegato generico può specificare l'argomento tipo per creare un tipo costruito chiuso, proprio come per la creazione di un'istanza di una classe generica o la chiamata di un metodo generico, come mostrato nell'esempio seguente:  
  
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
- [Guida per programmatori C#](../index.md)
- [Introduzione ai generics](./index.md)
- [Metodi generici](./generic-methods.md)
- [Classi generiche](./generic-classes.md)
- [Interfacce generiche](./generic-interfaces.md)
- [Delegati](../delegates/index.md)
- [Generics](../../../standard/generics/index.md)
