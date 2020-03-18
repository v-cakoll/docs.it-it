---
title: Uso delle proprietà - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- set accessor [C#]
- get accessor [C#]
- properties [C#], about properties
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
ms.openlocfilehash: d873f626b660bb6bd94710add4543e21e11823d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77452019"
---
# <a name="using-properties-c-programming-guide"></a>Utilizzo delle proprietà (Guida per programmatori C#)

Le proprietà combinano gli aspetti sia dei campi che dei metodi. Per l'utente di un oggetto, una proprietà si presenta come un campo: l'accesso alla proprietà richiede la stessa sintassi. Per il responsabile dell'implementazione di una classe, una proprietà è costituita da uno o due blocchi di codice, che rappresentano una funzione di accesso [get](../../language-reference/keywords/get.md) e/o una funzione di accesso [set](../../language-reference/keywords/set.md). Il blocco di codice per la funzione di accesso `get` viene eseguito al momento della lettura della proprietà; il blocco di codice per la funzione di accesso `set` viene eseguito quando viene assegnato un nuovo valore alla proprietà. Una proprietà senza una funzione di accesso `set` viene considerata di sola lettura. Una proprietà senza una funzione di accesso `get` viene considerata di sola scrittura. Una proprietà con entrambe le funzioni di accesso è di lettura/scrittura.

A differenza dei campi, le proprietà non sono classificate come variabili. Non è pertanto possibile passare una proprietà come un parametro [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md).

Le proprietà possono essere usate per diversi scopi: possono convalidare i dati prima di consentire una modifica, esporre in modo trasparente i dati in una classe in cui i dati vengono effettivamente recuperati da un'altra origine come un database oppure eseguire un'azione quando i dati vengono modificati, ad esempio generare un evento o modificare il valore di altri campi.

Le proprietà sono dichiarate nel blocco della classe specificando il livello di accesso del campo, seguito dal tipo della proprietà, seguito dal nome della proprietà, seguito da un blocco di codice che dichiara una funzione di accesso `get` e/o una funzione di accesso `set`. Ad esempio:

[!code-csharp[csProgGuideProperties#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#7)]

In questo esempio, `Month` è dichiarato come una proprietà in modo che la funzione di accesso `set` possa verificare che il valore `Month` sia compreso tra 1 e 12. La proprietà `Month` usa un campo privato per tenere traccia del valore effettivo. La posizione reale dei dati di una proprietà è spesso denominata "archivio di backup" della proprietà. Generalmente, le proprietà usano campi privati come archivio di backup. Il campo viene contrassegnato come privato per assicurare che possa essere modificato solo chiamando la proprietà. Per altre informazioni sulle restrizioni di accesso pubblico e privato, vedere [Modificatori di accesso](./access-modifiers.md).

Le proprietà implementate automaticamente forniscono una sintassi semplificata per le dichiarazioni di proprietà semplici. Per altre informazioni, vedere [Proprietà implementate automaticamente](auto-implemented-properties.md).

## <a name="the-get-accessor"></a>Funzione di accesso get

Il corpo della funzione di accesso `get` è simile a quello di un metodo. Deve restituire un valore del tipo di proprietà. L'esecuzione della funzione di accesso `get` è equivalente alla lettura del valore del campo. Ad esempio, quando si restituisce la variabile privata dalla funzione di accesso `get` e le ottimizzazioni sono abilitate, la chiamata al metodo della funzione di accesso `get` viene impostata come inline dal compilatore, pertanto non c'è alcun overhead di chiamata al metodo. Tuttavia, un metodo della funzione di accesso `get` virtuale non può essere impostato come inline perché il compilatore non può stabilire in fase di compilazione quale metodo potrebbe essere effettivamente chiamato in fase di esecuzione. Di seguito è riportata una funzione di accesso `get` che restituisce il valore di un campo privato `_name`:

[!code-csharp[csProgGuideProperties#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#8)]

Quando si fa riferimento alla proprietà, tranne che come destinazione di un'assegnazione, viene chiamata la funzione di accesso `get` per leggere il valore della proprietà. Ad esempio:

[!code-csharp[csProgGuideProperties#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#9)]

La funzione di accesso `get` deve terminare con un'istruzione [return](../../language-reference/keywords/return.md) o [throw](../../language-reference/keywords/throw.md) e il controllo non può uscire dal corpo della funzione di accesso.

È preferibile evitare di modificare lo stato dell'oggetto usando la funzione di accesso `get`. La seguente funzione di accesso, ad esempio, produce l'effetto collaterale di cambiare lo stato dell'oggetto ogni volta che si accede al campo `_number`.

[!code-csharp[csProgGuideProperties#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#10)]

La funzione di accesso `get` può essere usata per restituire il valore del campo o per calcolarlo e restituirlo. Ad esempio:

[!code-csharp[csProgGuideProperties#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#11)]

Nel segmento di codice precedente, se non `Name` si assegna un `NA`valore alla proprietà, verrà restituito il valore .

## <a name="the-set-accessor"></a>Funzione di accesso set

La funzione di accesso `set` è simile a un metodo il cui tipo restituito è [void](../../language-reference/builtin-types/void.md). Usa un parametro implicito denominato `value`, il cui tipo è il tipo della proprietà. Nell'esempio seguente, viene aggiunta una funzione di accesso `set` alla proprietà `Name`:

[!code-csharp[csProgGuideProperties#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#12)]

Quando si assegna un valore alla proprietà, viene richiamata la funzione di accesso `set` tramite un argomento che fornisce il nuovo valore. Ad esempio:

[!code-csharp[csProgGuideProperties#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#13)]

È un errore usare il nome del parametro implicito, `value`, per una dichiarazione di variabile locale in una funzione di accesso `set`.

## <a name="remarks"></a>Osservazioni

Le proprietà possono essere contrassegnate come `public`, `private`, `protected`, `internal`, `protected internal` o `private protected`. Questi modificatori di accesso definiscono in che modo gli utenti della classe possono accedere alla proprietà. Le funzioni di accesso `get` e `set` per la stessa proprietà possono avere modificatori di accesso diversi. Ad esempio, `get` potrebbe essere `public` per consentire l'accesso in sola lettura dall'esterno del tipo e `set` potrebbe essere `private` o `protected`. Per altre informazioni, vedere [Modificatori di accesso](./access-modifiers.md).

Una proprietà può essere dichiarata come proprietà statica tramite la parola chiave `static`. Questo rende la proprietà disponibile per i chiamanti in qualsiasi momento, anche se non esiste alcuna istanza della classe. Per ulteriori informazioni, vedere [Classi statiche e Membri di classi statiche](./static-classes-and-static-class-members.md).

Una proprietà può essere contrassegnata come virtuale mediante la parola chiave [virtual](../../language-reference/keywords/virtual.md). Ciò consente alle classi derivate di eseguire l'override del comportamento della proprietà tramite la parola chiave [override](../../language-reference/keywords/override.md). Per altre informazioni su queste opzioni, vedere [Ereditarietà](inheritance.md).

Una proprietà che esegue l'override di una proprietà virtuale può anche essere contrassegnata come [sealed](../../language-reference/keywords/sealed.md), in modo che non risulti più virtuale per le classi derivate. Infine, una proprietà può essere dichiarata [astratta](../../language-reference/keywords/abstract.md). Ciò significa che non vi è alcuna implementazione nella classe e le classi derivate devono scrivere la propria implementazione. Per altre informazioni su queste opzioni, vedere [Classi e membri delle classi astratte e sealed](abstract-and-sealed-classes-and-class-members.md).
  
> [!NOTE]
> È un errore usare un modificatore [virtual](../../language-reference/keywords/virtual.md), [abstract](../../language-reference/keywords/abstract.md) o [override](../../language-reference/keywords/override.md) in una funzione di accesso di una proprietà [statica](../../language-reference/keywords/static.md).

## <a name="example"></a>Esempio

Questo esempio illustra le proprietà di istanza, statiche e di sola lettura. Accetta il nome del dipendente dalla tastiera, incrementa `NumberOfEmployees` di 1 e visualizza il nome e il numero del dipendente.

[!code-csharp[csProgGuideProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#2)]

## <a name="example"></a>Esempio

In questo esempio viene illustrato come accedere a una proprietà in una classe base nascosta da un'altra proprietà con lo stesso nome in una classe derivata:This example demonstrates how to access a property in a base class that is hidden by another property that has the same name in a derived class:

[!code-csharp[csProgGuideProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#3)]

Di seguito sono riportati gli aspetti più importanti relativi all'esempio precedente:

- La proprietà `Name` nella classe derivata nasconde la proprietà `Name` nella classe di base. In tal caso, viene usato il modificatore `new` nella dichiarazione della proprietà nella classe derivata:

     [!code-csharp[csProgGuideProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#4)]  

- Il cast `(Employee)` viene usato per accedere alla proprietà nascosta nella classe di base:

     [!code-csharp[csProgGuideProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#5)]

     Per altre informazioni su come nascondere i membri, vedere [Modificatore new](../../language-reference/keywords/new-modifier.md).

## <a name="example"></a>Esempio

In questo esempio, due classi, `Cube` e `Square`, implementano una classe astratta, `Shape`, ed eseguono l'override della proprietà astratta `Area`. Si noti l'uso del modificatore [override](../../language-reference/keywords/override.md) nelle proprietà. Il programma accetta il lato come input e calcola le aree per il quadrato e il cubo. Inoltre, accetta l'area come input e calcola il lato corrispondente per il quadrato e il cubo.

[!code-csharp[csProgGuideProperties#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#6)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Proprietà](properties.md)
- [Proprietà dell'interfaccia](interface-properties.md)
- [Proprietà implementate automaticamenteAuto-Implemented Properties](auto-implemented-properties.md)
