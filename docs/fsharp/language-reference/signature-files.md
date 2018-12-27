---
title: File delle firme
description: Informazioni su come usare F# per contenere le informazioni sulle firme pubbliche di un set di file di firma F# elementi, quali tipi, gli spazi dei nomi e i moduli del programma.
ms.date: 06/15/2018
ms.openlocfilehash: 88938309a7c2bd12428f06ba8088141fd5349e80
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613414"
---
# <a name="signatures"></a>Firme

Un file della firma contiene informazioni sulle firme pubbliche di un set di elementi del programma F#, ad esempio i tipi, gli spazi dei nomi e i moduli. Può essere usato per specificare l'accessibilità di questi elementi del programma.

## <a name="remarks"></a>Note

Per ogni file di codice F# è disponibile un *file della firma*, ossia un file con lo stesso nome del file di codice, ma con l'estensione fsi invece che fs. I file della firma possono essere aggiunti anche alla riga di comando di compilazione se si usa direttamente la riga di comando. Per distinguere tra file di codice e file della firma, a volte i file di codice vengono chiamati *file di implementazione*. In un progetto il file della firma deve precedere il file di codice associato.

Un file della firma descrive gli spazi dei nomi, i moduli, i tipi e i membri nel file di implementazione corrispondente. Le informazioni in un file della firma vengono usate per specificare le parti di codice nel file di implementazione corrispondente a cui è possibile accedere dal codice esterno al file di implementazione e le parti interne al file di implementazione. Gli spazi dei nomi, i moduli e i tipi inclusi nel file della firma devono essere un subset degli spazi dei nomi, dei moduli e dei tipi inclusi nel file di implementazione. Con le eccezioni descritte più avanti in questo argomento, gli elementi del linguaggio non elencati nel file della firma vengono considerati privati per il file di implementazione. Se non vengono trovati file della firma nel progetto o nella riga di comando, viene usata l'opzione di accessibilità predefinita.

Per altre informazioni sull'accessibilità predefinita, vedere [controllo di accesso](access-control.md).

In un file della firma non ripetere la definizione dei tipi e le implementazioni di ogni metodo o funzione. Usare invece la firma per ogni metodo e funzione, che consente di specificare in modo completo le funzionalità implementate da un modulo o da un frammento dello spazio dei nomi. La sintassi per una firma di tipo è uguale a quella usata nelle dichiarazioni del metodo astratto nelle interfacce e nelle classi astratte e viene anche mostrata da IntelliSense e dall'interprete F# fsi.exe quando visualizza correttamente l'input compilato.

Se le informazioni nella firma di tipo non sono sufficienti a indicare se il tipo è sealed o un tipo di interfaccia, è necessario aggiungere un attributo che indichi la natura del tipo al compilatore. Gli attributi usati per questo scopo vengono descritti nella tabella seguente.

|Attributo|Descrizione|
|---------|-----------|
|`[<Sealed>]`|Per un tipo senza membri astratti o che non deve essere esteso.|
|`[<Interface>]`|Per un tipo che corrisponde a un'interfaccia.|

Il compilatore genera un errore se gli attributi non sono coerenti tra la firma e la dichiarazione nel file di implementazione.

Usare la parola chiave `val` per creare una firma per un valore o un valore di funzione. La parola chiave `type` introduce una firma di tipo.

È possibile generare un file della firma usando l'opzione `--sig` del compilatore. In generale, i file FSI non vengono scritti manualmente. I file FSI vengono invece generati usando il compilatore, aggiunti al progetto, se disponibile, e modificati rimuovendo i metodi e le funzioni che non si vogliono rendere accessibili.

Esistono diverse regole per le firme di tipo:

- Le abbreviazioni del tipo in un file di implementazione non devono corrispondere a un tipo senza abbreviazione in un file della firma.

- I record e le unioni discriminate devono esporre tutti i campi oppure nessuno e i costruttori e l'ordine nella firma devono corrispondere all'ordine nel file di implementazione. Le classi possono visualizzare alcuni, tutti o nessun campo e metodo nella firma.

- Le classi e le strutture con costruttori devono esporre le dichiarazioni delle relative classi base (dichiarazione `inherits` ). Inoltre, le classi e le strutture con costruttori devono esporre tutti i metodi astratti e le dichiarazioni di interfaccia.

- I tipi di interfaccia devono visualizzare tutti i relativi metodi e interfacce.

Le regole per le firme di valore sono le seguenti:

- I modificatori per l'accessibilità (`public`, `internal`e così via) e i modificatori `inline` e `mutable` nella firma devono corrispondere a quelli nell'implementazione.

- Il numero di parametri di tipo generico (dedotti implicitamente o dichiarati esplicitamente) deve corrispondere e il tipo e i vincoli di tipo nei parametri di tipo generico devono corrispondere.

- Se viene usato l'attributo `Literal` , deve essere visualizzato sia nella firma che nell'implementazione e è necessario usare lo stesso valore letterale per entrambe.

- Il modello dei parametri (anche noto come *grado*) delle firme e delle implementazioni deve essere coerente.

- Se i nomi dei parametri in un file di firma sono diversi dai file di implementazione corrispondente, il nome nel file della firma da utilizzare in alternativa, che potrebbe causare problemi durante il debug o di profilatura. Se si vuole ricevere una notifica di tali mancate corrispondenze, Abilita avviso 3218 nel file di progetto o quando si richiama il compilatore (vedere `--warnon` sotto [le opzioni del compilatore](compiler-options.md)).

L'esempio di codice seguente mostra un esempio di file della firma che contiene lo spazio dei nomi, il modulo, il valore di funzione e le firme di tipo, oltre agli attributi appropriati. Mostra anche il file di implementazione corrispondente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9002.fs)]

Il codice seguente mostra il file di implementazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9001.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Controllo di accesso](access-control.md)
- [Opzioni del compilatore](compiler-options.md)
