---
title: Metodi di estensione - Guida per programmatori C#
ms.date: 03/19/2020
helpviewer_keywords:
- methods [C#], adding to existing types
- extension methods [C#]
- methods [C#], extension
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
ms.openlocfilehash: 5db2797870b6c2e1998f17f1d8e4df8aa3f95c9e
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241409"
---
# <a name="extension-methods-c-programming-guide"></a>Metodi di estensione (Guida per programmatori C#)

I metodi di estensione consentono di "aggiungere" metodi ai tipi esistenti senza creare un nuovo tipo derivato, ricompilare o modificare in altro modo il tipo originale. I metodi di estensione sono metodi statici, ma vengono chiamati come se fossero metodi di istanza sul tipo esteso. Per il codice client scritto in C#, F # e Visual Basic, non esiste alcuna differenza evidente tra la chiamata di un metodo di estensione e i metodi definiti in un tipo.

I metodi di estensione più comuni sono gli operatori di query standard LINQ che aggiungono la funzionalità di query ai <xref:System.Collections.IEnumerable?displayProperty=nameWithType> tipi e esistenti <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . Per utilizzare gli operatori query standard, inserirli innanzitutto nell'ambito con una direttiva `using System.Linq`. In questo modo qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> avrà apparentemente metodi di istanza quali <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>e così via. È possibile visualizzare questi metodi aggiuntivi con la funzionalità di completamento istruzioni di IntelliSense quando si digita "punto" dopo un'istanza di un tipo <xref:System.Collections.Generic.IEnumerable%601>, ad esempio <xref:System.Collections.Generic.List%601> o <xref:System.Array>.

### <a name="orderby-example"></a>Esempio di OrderBy

Nell'esempio seguente viene illustrato come chiamare il metodo `OrderBy` dell'operatore query standard su una matrice di Integer. L'espressione tra parentesi è un'espressione lambda. Molti operatori di query standard accettano espressioni lambda come parametri, ma questo non è un requisito per i metodi di estensione. Per altre informazioni, vedere [espressioni lambda](../statements-expressions-operators/lambda-expressions.md).

[!code-csharp[csProgGuideExtensionMethods#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#3)]

I metodi di estensione sono definiti come metodi statici, ma vengono chiamati utilizzando la sintassi del metodo di istanza. Il primo parametro specifica il tipo su cui opera il metodo. Il parametro è preceduto dal modificatore [this](../../language-reference/keywords/this.md) . I metodi di estensione si trovano nell'ambito solo quando si importa in modo esplicito lo spazio dei nomi nel codice sorgente con una direttiva `using`.

Nell'esempio riportato di seguito viene illustrato un metodo di estensione definito per la classe <xref:System.String?displayProperty=nameWithType>. Viene definito all'interno di una classe statica non annidata e non generica:

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

Il metodo di estensione viene richiamato nel codice con la sintassi del metodo di istanza. Il linguaggio intermedio (IL) generato dal compilatore converte il codice in una chiamata sul metodo statico. Il principio di incapsulamento non viene effettivamente violato. I metodi di estensione non possono accedere a variabili private nel tipo che stanno estendendo.

Per ulteriori informazioni, vedere [come implementare e chiamare un metodo di estensione personalizzato](./how-to-implement-and-call-a-custom-extension-method.md).

In generale, probabilmente si chiamerà metodi di estensione molto più spesso rispetto all'implementazione di un proprio. Perché i metodi di estensione vengono chiamati utilizzando la sintassi del metodo di istanza, non è necessaria alcuna particolare conoscenza per utilizzarli dal codice client. Per abilitare i metodi di estensione per un particolare tipo, aggiungere una direttiva `using` per lo spazio dei nomi nel quale sono definiti i metodi. Per utilizzare ad esempio gli operatori query standard, aggiungere questa direttiva `using` al codice:

```csharp
using System.Linq;
```

Potrebbe anche essere necessario aggiungere un riferimento a System. Core. dll. Si noterà che gli operatori di query standard vengono ora visualizzati in IntelliSense come metodi aggiuntivi disponibili per la maggior parte dei <xref:System.Collections.Generic.IEnumerable%601> tipi.

## <a name="binding-extension-methods-at-compile-time"></a>Associazione di metodi di estensione in fase di compilazione

È possibile utilizzare metodi di estensione per estendere una classe o un'interfaccia, ma non per eseguirne l'override. Un metodo di estensione con lo stesso nome e la stessa firma di un metodo di interfaccia o di classe non verrà mai chiamato. In fase di compilazione, i metodi di estensione hanno sempre una priorità più bassa dei metodi di istanza definiti nel tipo stesso. In altre parole, se un tipo dispone di un metodo denominato `Process(int i)` e si dispone di un metodo di estensione con la stessa firma, il compilatore eseguirà sempre l'associazione al metodo di istanza. Quando il compilatore rileva una chiamata al metodo, cerca innanzitutto una corrispondenza nei metodi di istanza del tipo. Se non viene trovata alcuna corrispondenza, cercherà eventuali metodi di estensione definiti per il tipo ed eseguirà l'associazione al primo metodo di estensione trovato. Nell'esempio seguente viene dimostrato come il compilatore determina a quale metodo di estensione o metodo di istanza eseguire l'associazione.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono illustrate le regole che il compilatore C# segue nel determinare se associare una chiamata al metodo a un metodo di istanza sul tipo o a un metodo di estensione. La classe `Extensions` statica contiene metodi di estensione definiti per qualsiasi tipo che implementa `IMyInterface`. Le classi `A`, `B` e `C` implementano tutte l'interfaccia.

Il metodo di estensione `MethodB` non viene mai chiamato perché il nome e la firma corrispondono esattamente a metodi già implementati dalle classi.

Quando il compilatore non riesce a trovare un metodo di istanza con una firma corrispondente, eseguirà l'associazione a un metodo di estensione corrispondente se ne esiste uno.

[!code-csharp[csProgGuideExtensionMethods#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#5)]

## <a name="common-usage-patterns"></a>Modelli di utilizzo comuni

### <a name="collection-functionality"></a>Funzionalità di raccolta

In passato, era comune creare "classi di raccolta" che implementavano l' <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia per un determinato tipo e conteneva la funzionalità che agiva sulle raccolte di quel tipo. Anche se non c'è niente di sbagliato nella creazione di questo tipo di oggetto Collection, è possibile ottenere la stessa funzionalità usando un'estensione in <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . Le estensioni offrono il vantaggio di consentire la chiamata della funzionalità da qualsiasi raccolta, ad esempio <xref:System.Array?displayProperty=nameWithType> o <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> che implementi <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> in tale tipo. Un esempio di questo esempio di utilizzo di una matrice di Int32 è disponibile [in precedenza in questo articolo](#orderby-example).

### <a name="layer-specific-functionality"></a>Funzionalità specifiche del livello

Quando si usa un'architettura a cipolla o un'altra progettazione di applicazioni a più livelli, è comune avere un set di entità di dominio o oggetti Trasferimento dati che possono essere usati per comunicare tra i limiti dell'applicazione. Questi oggetti in genere non contengono funzionalità o solo funzionalità minime che si applicano a tutti i livelli dell'applicazione. I metodi di estensione possono essere usati per aggiungere funzionalità specifiche per ogni livello dell'applicazione senza caricare l'oggetto con metodi non necessari o desiderati in altri livelli.

```aspx-csharp
public class DomainEntity
{
    public int Id { get; set; }
    public string FirstName { get; set; }
    public string LastName { get; set; }
}

static class DomainEntityExtensions
{
    static string FullName(this DomainEntity value)
        => $"{value.FirstName} {value.LastName}";
}
```

### <a name="extending-predefined-types"></a>Estensione di tipi predefiniti

Anziché creare nuovi oggetti quando è necessario creare funzionalità riutilizzabili, è spesso possibile estendere un tipo esistente, ad esempio un tipo .NET o CLR. Ad esempio, se non si usano i metodi di estensione, è possibile creare `Engine` una `Query` classe o per eseguire il lavoro di esecuzione di una query su un SQL Server che può essere chiamato da più posizioni nel codice. Tuttavia, è possibile estendere la <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> classe usando i metodi di estensione per eseguire la query da qualsiasi luogo in cui è presente una connessione a una SQL Server. Altri esempi potrebbero consistere nell'aggiungere funzionalità comuni alla <xref:System.String?displayProperty=nameWithType> classe, estendere le funzionalità di elaborazione dei dati <xref:System.IO.File?displayProperty=nameWithType> degli <xref:System.IO.Stream?displayProperty=nameWithType> oggetti e e <xref:System.Exception?displayProperty=nameWithType> gli oggetti per una specifica funzionalità di gestione degli errori. Questi tipi di casi d'uso sono limitati solo dalla propria immaginazione e dal buon senso.

L'estensione dei tipi predefiniti può essere difficile con i `struct` tipi perché vengono passati per valore ai metodi. Ciò significa che vengono apportate modifiche allo struct a una copia dello struct. Queste modifiche non sono visibili quando il metodo di estensione viene chiuso. A partire da C# 7,2, è possibile aggiungere il `ref` modificatore al primo argomento di un metodo di estensione. L'aggiunta del `ref` modificatore indica che il primo argomento viene passato per riferimento. In questo modo è possibile scrivere metodi di estensione che modificano lo stato dello struct esteso.

## <a name="general-guidelines"></a>Linee guida generali

Sebbene sia ancora considerato preferibile aggiungere funzionalità modificando il codice di un oggetto o derivando un nuovo tipo ogni volta che è ragionevole ed è possibile farlo, i metodi di estensione sono diventati un'opzione cruciale per la creazione di funzionalità riutilizzabili nell'ecosistema .NET. Per le situazioni in cui l'origine originale non è sotto il controllo, quando un oggetto derivato è inappropriato o impossibile oppure quando la funzionalità non deve essere esposta oltre l'ambito applicabile, i metodi di estensione rappresentano una scelta ottimale.

Per ulteriori informazioni sui tipi derivati, vedere [ereditarietà](./inheritance.md).

Quando si usa un metodo di estensione per estendere un tipo il cui codice sorgente non è in grado di controllare, si corre il rischio che una modifica nell'implementazione del tipo provochi l'interruzione del metodo di estensione.

Se si implementano metodi di estensione per un determinato tipo, è importante tenere presente quanto segue:

- Un metodo di estensione non verrà mai chiamato se dispone della stessa firma di un metodo definito nel tipo.
- I metodi di estensione vengono inseriti nell'ambito al livello dello spazio dei nomi. Se, ad esempio, sono presenti più classi statiche che contengono metodi di estensione in un singolo spazio dei nomi denominato `Extensions` , verranno tutti inseriti nell'ambito `using Extensions;` dalla direttiva.

Per una libreria di classi implementata, non è necessario utilizzare i metodi di estensione per evitare l'incremento del numero di versione di un assembly. Se si desidera aggiungere funzionalità significative a una libreria per la quale si è proprietari del codice sorgente, attenersi alle linee guida di .NET per il controllo delle versioni degli assembly. Per altre informazioni, vedere [Controllo delle versioni degli assembly](../../../standard/assembly/versioning.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Esempi di programmazione parallela (sono inclusi molti metodi di estensione di esempio)](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
- [Espressioni lambda](../statements-expressions-operators/lambda-expressions.md)
- [Cenni preliminari sugli operatori di query standard](../concepts/linq/standard-query-operators-overview.md)
- [Regole di conversione per parametri Instance e relativo impatto](https://docs.microsoft.com/archive/blogs/sreekarc/conversion-rules-for-instance-parameters-and-their-impact)
- [Interoperabilità dei metodi di estensione tra linguaggi](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-interoperability-between-languages)
- [Metodi di estensione e delegati sottoposti a currying](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-and-curried-delegates)
- [Associazione di metodi di estensione e segnalazione errori](https://docs.microsoft.com/archive/blogs/sreekarc/extension-method-binding-and-error-reporting)
