---
title: Vantaggi dei generics (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b05a3a695064764618564293e6ccd92e2ce60be
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="benefits-of-generics-c-programming-guide"></a>Vantaggi dei generics (Guida per programmatori C#)
I generics rappresentano la soluzione a una limitazione in versioni precedenti di Common Language Runtime e del linguaggio C# nelle quali la generalizzazione viene effettuata tramite il casting dei tipi nel e dal tipo di base universale <xref:System.Object>. Creando una classe generica, è possibile creare una raccolta indipendente dai tipi in fase di compilazione.  
  
 Per una dimostrazione delle limitazioni dell'uso di classi di raccolta non generiche, è possibile scrivere un breve programma che usa la classe di raccolta <xref:System.Collections.ArrayList> dalla libreria di classi .NET Framework. <xref:System.Collections.ArrayList> è una classe di raccolta estremamente utile che può essere usata senza alcuna modifica per archiviare qualsiasi tipo riferimento o valore.  
  
 [!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 La comodità ha tuttavia un costo. Per qualsiasi tipo riferimento o valore aggiunto a <xref:System.Collections.ArrayList> viene effettuato l'upcast implicito a <xref:System.Object>. Se gli elementi sono tipi valore, devono essere sottoposti a conversione boxing quando vengono aggiunti all'elenco e a conversione unboxing quando vengono recuperati. Sia il casting che le operazioni di conversione boxing e unboxing riducono le prestazioni. L'effetto delle conversioni boxing e unboxing può essere molto significativo in scenari in cui è necessario scorrere raccolte di grandi dimensioni.  
  
 L'altra limitazione è la mancanza di un controllo dei tipi in fase di compilazione. Dato che <xref:System.Collections.ArrayList> effettua il cast di tutti gli elementi in <xref:System.Object>, non esiste alcun modo in fase di compilazione per evitare che il codice client esegua operazioni simili alle seguenti:  
  
 [!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 Anche se perfettamente accettabile e talvolta intenzionale se si sta creando un raccolta eterogenea, la combinazione di stringhe e `ints` in un singolo <xref:System.Collections.ArrayList> è più probabile che sia un errore di programmazione e questo errore non viene rilevato fino alla fase di esecuzione.  
  
 Nelle versioni 1.0 e 1.1 del linguaggio C#, è possibile evitare i pericoli del codice generalizzato nelle classi di raccolta della libreria di classi base di .NET Framework solo scrivendo raccolte personalizzate per tipi specifici. Naturalmente, dato che una classe di questo tipo non è riutilizzabile per più di un tipo di dati, si perdono i vantaggi della generalizzazione ed è necessario riscrivere la classe per ogni tipo che verrà archiviato.  
  
 Quello che serve effettivamente per <xref:System.Collections.ArrayList> e altre classi simili è un modo per specificare nel codice client, per ogni singola istanza, il tipo di dati specifico che si intende usare. In questo modo risulta inutile l'upcast a `T:System.Object` e il compilatore è inoltre in grado di eseguire il controllo dei tipi. In altre parole, <xref:System.Collections.ArrayList> richiede un parametro di tipo. Questo è esattamente ciò che offre la funzionalità generics. Nella raccolta generica <xref:System.Collections.Generic.List%601>, nello spazio dei nomi `N:System.Collections.Generic` la stessa operazione di aggiunta di elementi alla raccolta è simile all'esempio seguente:  
  
 [!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 Per il codice client, l'unica sintassi aggiunta con <xref:System.Collections.Generic.List%601> rispetto a <xref:System.Collections.ArrayList> è l'argomento di tipo nella dichiarazione e nella creazione dell'istanza. Al costo di codice leggermente più complesso, è possibile creare un elenco che non è solo più sicuro di <xref:System.Collections.ArrayList>, ma anche molto più rapido, specialmente quando gli elementi dell'elenco sono tipi valore.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)   
 [Procedure consigliate per le raccolte](http://go.microsoft.com/fwlink/?LinkId=112403)

