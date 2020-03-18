---
title: Controllo delle versioni di C# - Guida a C#
description: Informazioni sul funzionamento del controllo delle versioni in C# e .NET
ms.date: 01/08/2017
ms.technology: csharp-advanced-concepts
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: 124cce51865f04a555bc121fb6ce18cc95591bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156467"
---
# <a name="versioning-in-c"></a>Controllo delle versioni in C\#

In questa esercitazione si apprenderà il significato del controllo delle versioni in .NET. Verranno anche presentati i fattori da considerare durante il controllo delle versioni della libreria e verrà descritto l'aggiornamento a una nuova versione di una libreria.

## <a name="authoring-libraries"></a>Creazione di librerie

Gli sviluppatori che hanno creato le librerie .NET per uso pubblico probabilmente si sono trovati in situazioni in cui è necessario distribuire i nuovi aggiornamenti. Le modalità di gestione di questo processo sono molto importanti poiché è necessario garantire che non si verifichino problemi durante la transizione del codice esistente alla nuova versione della libreria. Ecco alcuni aspetti da considerare quando si crea una nuova versione:

### <a name="semantic-versioning"></a>Versionamento Semantico

[Versionamento Semantico](https://semver.org/) (SemVer per brevità) è una convenzione di denominazione applicata alle versioni della libreria per indicare cardine specifici.
In teoria, le informazioni sulla versione applicate alla libreria consentono agli sviluppatori di determinare la compatibilità con i progetti che usano versioni precedenti di quella libreria.

L'approccio di base a SemVer è il formato a 3 componenti `MAJOR.MINOR.PATCH`, dove:

- `MAJOR` viene incrementato quando si apportano modifiche incompatibili all'API
- `MINOR` viene incrementato quando si aggiungono funzionalità compatibili con le versioni precedenti
- `PATCH` viene incrementato quando si apportano correzioni dei bug compatibili con le versioni precedenti

Esistono anche dei modi per specificare altri scenari, ad esempio le versioni non definitive, quando si applicano le informazioni sulla versione alla libreria .NET.

### <a name="backwards-compatibility"></a>Compatibilità con le versioni precedenti

Quando si rilasciano nuove versioni della libreria, la compatibilità con le versioni precedenti probabilmente è una delle principali preoccupazioni.
Una nuova versione della libreria è compatibile a livello di codice sorgente con una versione precedente se il codice che dipende dalla versione precedente, quando viene ricompilato, funziona con la nuova versione.
Una nuova versione della libreria è compatibile a livello binario se un'applicazione che dipende dalla versione precedente funziona, senza ricompilazione, con la nuova versione.

Di seguito sono riportati alcuni aspetti da considerare quando si tenta di gestire la compatibilità della libreria con le versioni precedenti:

- Metodi virtuali: quando si trasforma un metodo virtuale in non virtuale nella nuova versione, sarà necessario aggiornare i progetti che eseguono l'override di tale metodo. Questa è una modifica sostanziale di grande impatto ed è fortemente sconsigliata.
- Firme del metodo: quando si aggiorna il comportamento di un metodo è necessario modificare anche la firma, è invece necessario creare un overload in modo che il codice che chiama in tale metodo continuerà a funzionare.
È sempre possibile modificare la firma del metodo precedente per chiamare la firma del nuovo metodo in modo che l'implementazione resti coerente.
- [Attributo Obsolete](programming-guide/concepts/attributes/common-attributes.md#Obsolete): è possibile usare questo attributo nel codice per specificare le classi o i membri di classe deprecati che potrebbero essere rimossi nelle versioni future. Ciò consente di predisporre meglio gli sviluppatori che usano la libreria a eventuali modifiche di rilievo.
- Argomenti di metodo facoltativi: se si rendono obbligatori argomenti di metodo che in precedenza erano facoltativi o si modifica il valore predefinito degli argomenti, tutto il codice che non specifica tali argomenti dovrà essere aggiornato.

> [!NOTE]
> Rendere facoltativi gli argomenti facoltativi dovrebbe avere pochissimo effetto, soprattutto se non modifica il comportamento del metodo.

Più è facile per gli utenti eseguire l'aggiornamento alla nuova versione della libreria, più rapido sarà l'aggiornamento.

### <a name="application-configuration-file"></a>File di configurazione dell'applicazione

Gli sviluppatori .NET molto probabilmente hanno trovato [il file `app.config`](../framework/configure-apps/file-schema/index.md) nella maggior parte dei tipi di progetto.
Questo semplice file di configurazione è in grado di ottimizzare la distribuzione dei nuovi aggiornamenti. In genere è necessario progettare le librerie in modo che le `app.config` informazioni che potrebbero cambiare regolarmente vengono memorizzate nel file, in questo modo quando tali informazioni vengono aggiornate, il file di configurazione delle versioni precedenti deve solo essere sostituito con quello nuovo senza la necessità di ricompilazione della libreria.

## <a name="consuming-libraries"></a>Elaborazione delle librerie

Uno sviluppatore che elabora librerie .NET compilate da altri sviluppatori probabilmente sa che una nuova versione di una libreria potrebbe non essere completamente compatibile con il progetto e che spesso è necessario aggiornare il codice perché funzioni con le modifiche.

Fortunatamente per te, il linguaggio .NET e l'ecosistema .NET sono dotati di funzionalità e tecniche che consentono di aggiornare facilmente la nostra app per lavorare con nuove versioni di librerie che potrebbero introdurre modifiche di rilievo.

### <a name="assembly-binding-redirection"></a>Reindirizzamento dell'associazione di assembly

Puoi usare il file *app.config* per aggiornare la versione di una raccolta usata dall'app. Aggiungendo quello che viene chiamato [*un reindirizzamento dell'associazione*](../framework/configure-apps/redirect-assembly-versions.md), è possibile utilizzare la nuova versione della libreria senza dover ricompilare l'app. L'esempio seguente mostra come aggiornare il file *app.config* dell'app per usare la `1.0.1` versione della patch anziché `ReferencedLibrary` la `1.0.0` versione con cui è stata compilata in origine.

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> Questo approccio funziona solo se la nuova versione di `ReferencedLibrary` è compatibile a livello binario con l'applicazione.
> Vedere la sezione [Compatibilità con le versioni precedenti](#backwards-compatibility) per verificare quando deve essere determinata la compatibilità.

### <a name="new"></a>Nuovo

Usare il modificatore `new` per nascondere i membri ereditati di una classe di base. In questo modo le classi derivate possono rispondere agli aggiornamenti nelle classi di base.

Vedere l'esempio seguente:

[!code-csharp[Sample usage of the 'new' modifier](~/samples/snippets/csharp/versioning/new/Program.cs#sample)]

**Output**

```console
A base method
A derived method
```

Nell'esempio precedente si può vedere come `DerivedClass` nasconde il metodo `MyMethod` presente in `BaseClass`.
Ciò significa che quando una classe di base nella nuova versione di una libreria aggiunge un membro già esistente nella classe derivata, è sufficiente usare il modificatore `new` per il membro della classe derivata per nascondere il membro della classe di base.

Se non si specifica alcun modificatore `new`, una classe derivata nasconderà per impostazione predefinita i membri in conflitto in una classe di base e il codice verrà comunque compilato anche se viene generato un avviso del compilatore. Ciò significa che la semplice aggiunta di nuovi membri a una classe esistente rende la nuova versione della libreria compatibile sia a livello di codice sorgente che a livello binario con il codice che dipende da essa.

### <a name="override"></a>override

Il modificatore `override` indica che un'implementazione derivata estende l'implementazione di un membro della classe di base anziché nasconderlo. È necessario che al membro della classe di base sia applicato il modificatore `virtual`.

[!code-csharp[Sample usage of the 'override' modifier](../../samples/snippets/csharp/versioning/override/Program.cs#sample)]

**Output**

```console
Base Method One: Method One
Derived Method One: Derived Method One
```

Il modificatore `override` viene valutato in fase di compilazione e il compilatore genera un errore se non trova un membro virtuale di cui eseguire l'override.

La vostra conoscenza delle tecniche discusse e la vostra comprensione delle situazioni in cui utilizzarle, andrà un lungo cammino verso l'allentamento della transizione tra le versioni di una libreria.
