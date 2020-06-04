---
title: Inizializzatori di raccolta
ms.date: 07/20/2015
f1_keywords:
- vb.CollectionInitializer
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
ms.openlocfilehash: 1d2d5adc7266faaa1636e568d6433429761eeaab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414544"
---
# <a name="collection-initializers-visual-basic"></a>Inizializzatori di raccolta (Visual Basic)

Gli *inizializzatori di insieme* consentono di creare una raccolta e popolarla con un set iniziale di valori. Gli inizializzatori di insieme sono utili quando si crea una raccolta da un set di valori noti, ad esempio un elenco di opzioni di menu o categorie, un set iniziale di valori numerici, un elenco statico di stringhe quali nomi di giorni o mesi o un elenco di aree geografiche, ad esempio un elenco di stati che viene usato per la convalida.

Per altre informazioni sulle raccolte, vedere [Raccolte](../../concepts/collections.md).

È possibile identificare un inizializzatore di insieme usando la parola chiave `From` seguita da parentesi graffe (`{}`). Questo approccio è simile alla sintassi dei valori letterali di matrice, descritta in [Matrici](../arrays/index.md). Gli esempi seguenti illustrano diversi metodi d'uso degli inizializzatori di insieme per la creazione di raccolte.

[!code-vb[VbVbalrCollectionInitializers#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#1)]

> [!NOTE]
> Anche C# offre inizializzatori di insieme. Gli inizializzatori di insieme di C# offrono la stessa funzionalità degli inizializzatori di insieme di Visual Basic. Per altre informazioni sugli inizializzatori di insieme di C#, vedere [Inizializzatori di oggetto e di insieme](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).

## <a name="syntax"></a>Sintassi

Un inizializzatore di insieme è costituito da un elenco di valori delimitati da virgole racchiusi tra parentesi graffe (`{}`) e preceduti dalla parola chiave `From` come illustrato nel codice seguente.

[!code-vb[VbVbalrCollectionInitializers#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#2)]

Quando si crea una raccolta, ad esempio <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>, è necessario specificare il tipo di raccolta prima dell'inizializzatore di insieme, come illustrato nel codice seguente.

[!code-vb[VbVbalrCollectionInitializers#13](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#13)]

> [!NOTE]
> È possibile combinare un inizializzatore di insieme e un inizializzatore di oggetto per inizializzare lo stesso oggetto raccolta. È possibile usare gli inizializzatori di oggetto per inizializzare oggetti in un inizializzatore di insieme.

## <a name="creating-a-collection-by-using-a-collection-initializer"></a>Creazione di una raccolta tramite un inizializzatore di raccolta

Quando si crea una raccolta usando un inizializzatore di insieme, ogni valore specificato nell'inizializzatore di insieme viene passato al metodo `Add` appropriato della raccolta. Se ad esempio si crea un <xref:System.Collections.Generic.List%601> usando un inizializzatore di insieme, ogni valore stringa nell'inizializzatore di insieme viene passato al metodo <xref:System.Collections.Generic.List%601.Add%2A>. Se si vuole creare una raccolta usando un inizializzatore di insieme, il tipo specificato deve essere un tipo di raccolta valido. Sono esempi di tipi di raccolta validi le classi che implementano l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> o ereditano la classe <xref:System.Collections.CollectionBase>. Il tipo specificato deve anche esporre un metodo `Add` che soddisfa i criteri seguenti.

- Il metodo `Add` deve essere disponibile dall'ambito in cui viene chiamato l'inizializzatore di insieme. Non è necessario che il metodo `Add` sia pubblico se l'inizializzatore di insieme è usato in uno scenario in cui è possibile accedere a metodi non pubblici della raccolta.

- Il metodo `Add` deve essere un membro di istanza o un membro `Shared` della classe di raccolta oppure un metodo di estensione.

- Deve esistere un metodo `Add` che può corrispondere ai tipi specificati nell'inizializzatore di insieme, in base alle regole di risoluzione dell'overload.

 Il codice di esempio seguente illustra come creare una raccolta `List(Of Customer)` usando un inizializzatore di insieme. Quando il codice viene eseguito ogni oggetto `Customer` viene passato al metodo `Add(Customer)` dell'elenco generico.

[!code-vb[VbVbalrCollectionInitializers#9](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#9)]

L'esempio di codice seguente visualizza codice equivalente che non usa un inizializzatore di insieme.

[!code-vb[VbVbalrCollectionInitializers#10](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#10)]

Se la raccolta ha un metodo `Add` con parametri che corrispondono al costruttore dell'oggetto `Customer` è possibile nidificare i valori dei parametri per il metodo `Add` all'interno di inizializzatori di insieme, come descritto nella sezione successiva. Se la raccolta non dispone di tale metodo `Add` è possibile crearne uno come metodo di estensione. Per un esempio di creazione di un metodo `Add` come metodo di estensione per una raccolta, vedere [Procedura: Creare un metodo di estensione Add usato da un inizializzatore di insieme](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md). Per un esempio di creazione di una raccolta personalizzata che può essere usata con un inizializzatore di insieme, vedere [Procedura: Creare una raccolta usata da un inizializzatore di insieme](how-to-create-a-collection-used-by-a-collection-initializer.md).

## <a name="nesting-collection-initializers"></a>Annidamento di inizializzatori di insieme

È possibile annidare valori in un inizializzatore di insieme per identificare un overload specifico di un metodo `Add` per la raccolta che viene creata. I valori passati al metodo `Add` devono essere separati da virgole e racchiusi tra parentesi graffe (`{}`), come nella sintassi di un valore letterale di matrice o di un inizializzatore di insieme.

Quando si crea una raccolta usando valori annidati ogni elemento dell'elenco di valori annidati viene passato come argomento al metodo `Add`, che corrisponde ai tipi di elemento. Ad esempio il codice seguente crea un <xref:System.Collections.Generic.Dictionary%602> in cui le chiavi sono di tipo `Integer` e i valori sono di tipo `String`. Ogni elenco di valori annidati viene associato al metodo <xref:System.Collections.Generic.Dictionary%602.Add%2A> per `Dictionary`.

[!code-vb[VbVbalrCollectionInitializers#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#5)]

Il codice dell'esempio precedente equivale al seguente codice.

[!code-vb[VbVbalrCollectionInitializers#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#6)]

Solo gli elenchi di valori annidati al primo livello di annidamento vengono inviati al metodo `Add` per il tipo di raccolta. I livelli di annidamento più profondi vengono considerati come valori letterali di matrice e gli elenchi di valori annidati non vengono associati al metodo `Add` di una raccolta.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|---|---|
|[Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|Illustra come creare un metodo di estensione denominato `Add` che può essere usato per popolare una raccolta con valori di un inizializzatore di insieme.|
|[Procedura: Creare una raccolta usata da un inizializzatore di raccolta](how-to-create-a-collection-used-by-a-collection-initializer.md)|Illustra come abilitare l'uso di un inizializzatore di insieme includendo un metodo `Add` in una classe di raccolte che implementa `IEnumerable`.|

## <a name="see-also"></a>Vedere anche

- [raccolte](../../concepts/collections.md)
- [Matrici](../arrays/index.md)
- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Operatore New](../../../language-reference/operators/new-operator.md)
- [Proprietà implementate automaticamente](../procedures/auto-implemented-properties.md)
- [Procedura: Inizializzare una variabile di matrice in Visual Basic](../arrays/how-to-initialize-an-array-variable.md)
- [Inferenza del tipo di variabile locale](../variables/local-type-inference.md)
- [Tipi anonimi](../objects-and-classes/anonymous-types.md)
- [Introduzione a LINQ in Visual Basic](../linq/introduction-to-linq.md)
- [Procedura: Creare un elenco di elementi](../../concepts/linq/how-to-create-a-list-of-items.md)
