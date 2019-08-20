---
title: Generics - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 7d212aeaa7d7a8c3f152f8610a7ef3fe5de0fe23
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589600"
---
# <a name="generics-c-programming-guide"></a>Generics (Guida per programmatori C#)
I generics sono stati aggiunti alla versione 2.0 del linguaggio C# e di Common Language Runtime (CLR). I generics introducono in .NET Framework il concetto dei parametri di tipo, che consentono di progettare classi e metodi che rinviano la specifica di uno o più tipi finché non si dichiara la classe o il metodo e si crea un'istanza dal codice client. Ad esempio, usando un parametro di tipo generico T è possibile scrivere un'unica classe che altro codice client può usare senza rischiare cast di runtime o operazioni di boxing, come illustrato di seguito:  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

Le classi e i metodi generici sono riutilizzabili, indipendenti dai tipi e molto più efficaci delle rispettive controparti non generiche. I generics sono in genere usati con le raccolte e i metodi che operano su di essi. La versione 2.0 della libreria di classi .NET Framework offre un nuovo spazio dei nomi, <xref:System.Collections.Generic>, che contiene diverse nuove classi di raccolta generiche. È consigliabile che tutte le applicazioni destinate a .NET Framework 2.0 e versioni successive usino le nuove classi di raccolte generiche anziché le controparti non generiche meno recenti, ad esempio <xref:System.Collections.ArrayList>. Per altre informazioni, vedere [Generics in .NET](../../../standard/generics/index.md).  
  
 Naturalmente, è anche possibile creare tipi e metodi generici personalizzati per offrire le proprie soluzioni e schemi progettuali generalizzati che sono indipendenti dai tipi ed efficienti. Nell'esempio di codice riportato di seguito viene illustrata una classe di elenco collegato generica semplice a scopo dimostrativo. Nella maggior parte dei casi, è necessario usare la classe <xref:System.Collections.Generic.List%601> specificata dalla libreria di classi .NET Framework anziché crearne una propria. Il parametro di tipo `T` viene usato in diverse posizioni in cui di norma verrebbe usato un tipo concreto per indicare il tipo dell'elemento archiviato nell'elenco. In particolare, viene usato nei seguenti modi:  
  
- Come tipo di un parametro del metodo nel metodo `AddHead`.  
  
- Come tipo restituito della proprietà `Data` nella classe `Node` annidata.  
  
- Come tipo del membro privato `data` nella classe annidata.  
  
 Si noti che T è disponibile per la classe `Node` annidata. Quando si crea un'istanza di `GenericList<T>` con un tipo concreto, ad esempio `GenericList<int>`, ogni occorrenza di `T` verrà sostituita con `int`.  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 Nell'esempio di codice riportato di seguito viene illustrato come il codice client usa la classe generica `GenericList<T>` per creare un elenco di interi. Cambiando semplicemente l'argomento relativo al tipo, è possibile modificare il codice riportato di seguito per creare elenchi di stringhe o di qualsiasi altro tipo personalizzato:  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a>Panoramica sui generics  
  
- Usare i tipi generici per ottimizzare il riutilizzo del codice, l'indipendenza dai tipi e le prestazioni.  
  
- L'uso più comune dei generics consiste nel creare classi di raccolte.  
  
- La libreria di classi .NET Framework contiene diverse nuove classi di raccolte generiche nello spazio dei nomi <xref:System.Collections.Generic>. Queste classi devono essere usate ogni volta che sia possibile al posto di classi come <xref:System.Collections.ArrayList> nello spazio dei nomi <xref:System.Collections>.  
  
- È possibile creare interfacce, classi, metodi, eventi e delegati generici.  
  
- Le classi generiche possono essere limitate in modo da abilitare l'accesso ai metodi per particolari tipi di dati.  
  
- Le informazioni sui tipi usati in un tipo di dati generico possono essere ottenute usando la reflection in fase di esecuzione.  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per ulteriori informazioni:  
  
- [Parametri di tipo generico](./generic-type-parameters.md)  
  
- [Vincoli sui parametri di tipo](./constraints-on-type-parameters.md)  
  
- [Classi generiche](./generic-classes.md)  
  
- [Interfacce generiche](./generic-interfaces.md)  
  
- [Metodi generici](./generic-methods.md)  
  
- [Delegati generici](./generic-delegates.md)  
  
- [Differenze tra modelli C++ e generics C#](./differences-between-cpp-templates-and-csharp-generics.md)  
  
- [Generics e reflection](./generics-and-reflection.md)  
  
- [Generics in fase di esecuzione](./generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 Per altre informazioni, vedere la [specifica del linguaggio C#](~/_csharplang/spec/types.md#constructed-types).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../index.md)
- [Tipi](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [Generics in .NET](../../../standard/generics/index.md)
