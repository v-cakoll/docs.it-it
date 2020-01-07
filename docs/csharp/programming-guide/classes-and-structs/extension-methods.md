---
title: Metodi di estensione - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], adding to existing types
- extension methods [C#]
- methods [C#], extension
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
ms.openlocfilehash: 66c8dee059d65f6628bf38edecf2f5abec320eea
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635834"
---
# <a name="extension-methods-c-programming-guide"></a>Metodi di estensione (Guida per programmatori C#)
I metodi di estensione consentono di "aggiungere" metodi ai tipi esistenti senza creare un nuovo tipo derivato, ricompilare o modificare in altro modo il tipo originale. I metodi di estensione sono uno speciale tipo di metodo statico, ma vengono chiamati come se fossero metodi di istanza sul tipo esteso. Per il codice client scritto in C#, F# e Visual Basic non esistono differenze evidenti tra la chiamata a un metodo di estensione e ai metodi effettivamente definiti in un tipo.  
  
 I metodi di estensione più comuni sono gli operatori di query standard LINQ che aggiungono la funzionalità di query ai tipi di <xref:System.Collections.IEnumerable?displayProperty=nameWithType> e di <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> esistenti. Per utilizzare gli operatori query standard, inserirli innanzitutto nell'ambito con una direttiva `using System.Linq`. In questo modo qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> avrà apparentemente metodi di istanza quali <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>e così via. È possibile visualizzare questi metodi aggiuntivi con la funzionalità di completamento istruzioni di IntelliSense quando si digita "punto" dopo un'istanza di un tipo <xref:System.Collections.Generic.IEnumerable%601>, ad esempio <xref:System.Collections.Generic.List%601> o <xref:System.Array>.  
  
 Nell'esempio seguente viene illustrato come chiamare il metodo `OrderBy` dell'operatore query standard su una matrice di Integer. L'espressione tra parentesi è un'espressione lambda. Molti operatori query standard accettano espressioni lambda come parametri, sebbene non sia un requisito per i metodi di estensione. Per altre informazioni, vedere [Espressioni lambda](../statements-expressions-operators/lambda-expressions.md).  
  
 [!code-csharp[csProgGuideExtensionMethods#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#3)]  
  
 I metodi di estensione sono definiti come metodi statici, ma vengono chiamati utilizzando la sintassi del metodo di istanza. Il primo parametro specifica su quale tipo opera il metodo ed è preceduto dal modificatore [this](../../language-reference/keywords/this.md). I metodi di estensione si trovano nell'ambito solo quando si importa in modo esplicito lo spazio dei nomi nel codice sorgente con una direttiva `using`.  
  
 Nell'esempio riportato di seguito viene illustrato un metodo di estensione definito per la classe <xref:System.String?displayProperty=nameWithType>. Si noti che viene definito in una classe statica non annidata e non generica:  
  
 [!code-csharp[csProgGuideExtensionMethods#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#4)]  
  
 Il metodo di estensione `WordCount` può essere inserito nell'ambito con questa direttiva `using`:  
  
```csharp  
using ExtensionMethods;  
```  
  
 Può inoltre essere chiamato da un'applicazione utilizzando questa sintassi:  
  
```csharp  
string s = "Hello Extension Methods";  
int i = s.WordCount();  
```  
  
 Nel codice si richiama il metodo di estensione con la sintassi del metodo di istanza. Microsoft Intermediate Language (IL) generato dal compilatore converte tuttavia il codice in una chiamata sul metodo statico. Il principio di incapsulamento non viene pertanto realmente violato. Infatti, i metodi di estensione non possono accedere a variabili private nel tipo che stanno estendendo.  
  
 Per ulteriori informazioni, vedere [come implementare e chiamare un metodo di estensione personalizzato](./how-to-implement-and-call-a-custom-extension-method.md).
  
 In generale, è molto più frequente chiamare i metodi di estensione che implementarne di personalizzati. Perché i metodi di estensione vengono chiamati utilizzando la sintassi del metodo di istanza, non è necessaria alcuna particolare conoscenza per utilizzarli dal codice client. Per abilitare i metodi di estensione per un particolare tipo, aggiungere una direttiva `using` per lo spazio dei nomi nel quale sono definiti i metodi. Per utilizzare ad esempio gli operatori query standard, aggiungere questa direttiva `using` al codice:  
  
```csharp  
using System.Linq;  
```  
  
 Potrebbe anche essere necessario aggiungere un riferimento a System. Core. dll. Si noterà che gli operatori di query standard vengono ora visualizzati in IntelliSense come metodi aggiuntivi disponibili per la maggior parte dei tipi di <xref:System.Collections.Generic.IEnumerable%601>.  
  
## <a name="binding-extension-methods-at-compile-time"></a>Associazione di metodi di estensione in fase di compilazione  
 È possibile utilizzare metodi di estensione per estendere una classe o un'interfaccia, ma non per eseguirne l'override. Un metodo di estensione con lo stesso nome e la stessa firma di un metodo di interfaccia o di classe non verrà mai chiamato. In fase di compilazione, i metodi di estensione hanno sempre una priorità più bassa dei metodi di istanza definiti nel tipo stesso. In altre parole, se un tipo dispone di un metodo denominato `Process(int i)` e si dispone di un metodo di estensione con la stessa firma, il compilatore eseguirà sempre l'associazione al metodo di istanza. Quando il compilatore rileva una chiamata al metodo, cerca innanzitutto una corrispondenza nei metodi di istanza del tipo. Se non viene trovata alcuna corrispondenza, cercherà eventuali metodi di estensione definiti per il tipo ed eseguirà l'associazione al primo metodo di estensione trovato. Nell'esempio seguente viene dimostrato come il compilatore determina a quale metodo di estensione o metodo di istanza eseguire l'associazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrate le regole che il compilatore C# segue nel determinare se associare una chiamata al metodo a un metodo di istanza sul tipo o a un metodo di estensione. La classe `Extensions` statica contiene metodi di estensione definiti per qualsiasi tipo che implementa `IMyInterface`. Le classi `A`, `B` e `C` implementano tutte l'interfaccia.  
  
 Il metodo di estensione `MethodB` non viene mai chiamato perché il nome e la firma corrispondono esattamente a metodi già implementati dalle classi.  
  
 Quando il compilatore non è in grado di trovare un metodo di istanza con una firma corrispondente, eseguirà l'associazione a un metodo di estensione corrispondente se esistente.  
  
 [!code-csharp[csProgGuideExtensionMethods#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#5)]  
  
## <a name="general-guidelines"></a>Indicazioni generali  
 In generale, si consiglia di implementare i metodi di estensione sporadicamente e solo se necessario. Se possibile, è opportuno che il codice client che deve estendere un tipo esistente esegua questa operazione creando un nuovo tipo derivato dal tipo esistente. Per altre informazioni, vedere [Ereditarietà](./inheritance.md).  
  
 Quando si utilizza un metodo di estensione per estendere un tipo di cui non è possibile modificare il codice sorgente, si corre il rischio che una modifica nell'implementazione del tipo provochi l'interruzione del metodo di estensione.  
  
 Se si implementano metodi di estensione per un determinato tipo, è importante tenere presente quanto segue:  
  
- Un metodo di estensione non verrà mai chiamato se dispone della stessa firma di un metodo definito nel tipo.  
  
- I metodi di estensione vengono inseriti nell'ambito al livello dello spazio dei nomi. Se, ad esempio, si dispone di più classi statiche contenenti metodi di estensione in un solo spazio dei nomi denominato `Extensions`, verranno tutti inseriti nell'ambito dalla direttiva `using Extensions;`.  
  
 Per una libreria di classi implementata, non è necessario utilizzare i metodi di estensione per evitare l'incremento del numero di versione di un assembly. Se si desidera aggiungere funzionalità significative a una libreria per il quale si è proprietari del codice sorgente, è necessario seguire le linee guida standard di .NET Framework per il controllo delle versioni degli assembly. Per altre informazioni, vedere [Controllo delle versioni degli assembly](../../../standard/assembly/versioning.md).  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Esempi di programmazione parallela (sono inclusi molti metodi di estensione di esempio)](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
- [Espressioni lambda](../statements-expressions-operators/lambda-expressions.md)
- [Cenni preliminari sugli operatori di query standard](../concepts/linq/standard-query-operators-overview.md)
- [Regole di conversione per parametri Instance e relativo impatto](https://blogs.msdn.microsoft.com/sreekarc/2007/10/11/conversion-rules-for-instance-parameters-and-their-impact)
- [Interoperabilità dei metodi di estensione tra linguaggi](https://blogs.msdn.microsoft.com/sreekarc/2007/10/11/extension-methods-interoperability-between-languages)
- [Metodi di estensione e delegati sottoposti a currying](https://blogs.msdn.microsoft.com/sreekarc/2007/05/01/extension-methods-and-curried-delegates)
- [Associazione di metodi di estensione e segnalazione errori](https://blogs.msdn.microsoft.com/sreekarc/2007/04/26/extension-method-binding-and-error-reporting)
