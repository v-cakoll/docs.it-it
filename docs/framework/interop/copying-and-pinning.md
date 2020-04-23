---
title: copia e blocco
ms.date: 03/30/2017
helpviewer_keywords:
- pinning, interop marshaling
- copying, interop marshaling
- interop marshaling, copying
- interop marshaling, pinning
ms.assetid: 0059f576-e460-4e70-b257-668870e420b8
ms.openlocfilehash: f6db7d37293015911c1285d39e19bf7542a7ac59
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123635"
---
# <a name="copying-and-pinning"></a>copia e blocco

Durante il marshalling il gestore di marshalling di interoperabilità può copiare o bloccare i dati interessati. Tramite l'operazione di copia, una copia dei dati viene spostata da una posizione della memoria a un'altra. La figura seguente illustra le differenze esistenti tra la copia di un tipo valore e quella di un tipo passato per riferimento dalla memoria gestita a quella non gestita.

![Diagramma che mostra come vengono copiati i tipi di riferimento e valore.](./media/copying-and-pinning/interop-marshal-copy.gif)

Il marshalling degli argomenti del metodo passati per valore a codice non gestito viene eseguito come marshalling di valori sullo stack. Il processo di copia è diretto. Gli argomenti passati per riferimento vengono passati come puntatori allo stack. Anche i tipi riferimento vengono passati per valore e per riferimento. Come illustrato nella figura seguente, i tipi riferimento passati per valore vengono copiati o bloccati:

![Diagramma che mostra i tipi riferimento passati per valore e per riferimento.](./media/copying-and-pinning/interop-marshal-reference-pin.gif)

Con il blocco, i dati vengono temporaneamente bloccati nella posizione di memoria corrente, impedendone quindi il riposizionamento da parte del Garbage Collector di Common Language Runtime. I dati vengono bloccati dal gestore di marshalling per ridurre il sovraccarico dell'operazione di copia e migliorare le prestazioni. In base al tipo, si stabilisce se i dati verranno copiati o bloccati nel corso del processo di marshalling.  Per oggetti come <xref:System.String>, il blocco viene eseguito automaticamente durante il marshalling. È tuttavia possibile bloccare la memoria manualmente tramite la classe <xref:System.Runtime.InteropServices.GCHandle>.

## <a name="formatted-blittable-classes"></a>Classi copiabili da BLT formattate

Le classi [copiabili da BLT](blittable-and-non-blittable-types.md) formattate hanno un layout fisso (formattato) e una rappresentazione dei dati comune sia nella memoria gestita che in quella non gestita. Quando questi tipi richiedono il marshalling, un puntatore all'oggetto nell'heap viene passato direttamente al chiamato, il quale può modificare il contenuto della posizione di memoria a cui il puntatore fa riferimento.

> [!NOTE]
> Il chiamato può modificare il contenuto della memoria se il parametro è contrassegnato come out o in/out. Al contrario, il chiamato deve evitare di modificare il contenuto quando il parametro è impostato su Marshal come in, che è l'impostazione predefinita per i tipi copiabili in formato. La modifica di un oggetto In genera problemi quando la stessa classe viene esportata in una libreria dei tipi e usata per effettuare chiamate su più apartment.

## <a name="formatted-non-blittable-classes"></a>Classi non copiabili da BLT formattate

Le classi [non copiabili da BLT](blittable-and-non-blittable-types.md) formattate hanno un layout fisso (formattato) ma la rappresentazione dei dati è diversa nella memoria gestita e in quella non gestita. Può essere necessaria la trasformazione dei dati nelle condizioni seguenti:

- Se si esegue il marshalling di una classe non copiabile da BLT per valore, il chiamato riceve un puntatore a una copia della struttura dei dati.

- Se si esegue il marshalling di una classe non copiabile da BLT per riferimento, il chiamato riceve un puntatore a un puntatore a una copia della struttura dei dati.

- Se si imposta l'attributo <xref:System.Runtime.InteropServices.InAttribute>, la copia viene sempre inizializzata con lo stato dell'istanza. Il marshalling viene eseguito secondo necessità.

- Se si imposta l'attributo <xref:System.Runtime.InteropServices.OutAttribute>, lo stato viene sempre restituito come copia all'istanza. Il marshalling viene eseguito secondo necessità.

- Se si impostano sia **InAttribute** che **OutAttribute**, sono richieste entrambe le copie. Se si omette uno degli attributi, il gestore di marshalling può ottimizzare il processo eliminando una delle copie.

## <a name="reference-types"></a>Tipi riferimento

È possibile passare i tipi riferimento per valore o per riferimento. Quando sono passati per valore, sullo stack viene passato un puntatore al tipo. Quando sono passati per riferimento, sullo stack viene passato un puntatore a un puntatore al tipo.

Il comportamento dei tipi riferimento varia a seconda delle condizioni seguenti:

- Se un tipo riferimento viene passato per valore e possiede membri di tipo non copiabile da BLT, i tipi vengono convertiti due volte:

  - Quando si passa un argomento al lato non gestito.

  - Al ritorno dalla chiamata.

  Per evitare inutili operazioni di copia e conversione, viene eseguito il marshalling di questi tipi come parametri In. Perché le modifiche apportate dal chiamato risultino visibili al chiamante, è necessario applicare gli attributi **InAttribute** e **OutAttribute** a un argomento in modo esplicito.

- Se un tipo riferimento viene passato per valore e possiede solo membri di tipi copiabili da BLT, è possibile bloccarlo durante il marshalling e le modifiche apportate ai membri del tipo dal chiamato saranno visibili al chiamante. Per ottenere questo comportamento, applicare **InAttribute** e **OutAttribute** in modo esplicito. Senza questi attributi direzionali, il gestore di marshalling di interoperabilità non esporta informazioni direzionali nella libreria dei tipi, ma come parametro In per impostazione predefinita. Potrebbero quindi verificarsi problemi con il marshalling su più apartment COM.

- Se si passa un tipo riferimento per riferimento, il marshalling viene eseguito come In/Out per impostazione predefinita.

## <a name="systemstring-and-systemtextstringbuilder"></a>System.String e System.Text.StringBuilder

Quando si esegue il marshalling dei dati nel codice non gestito per valore o per riferimento, in genere i dati vengono copiati dal gestore di marshalling in un buffer secondario, eventualmente convertendo i set di caratteri nel corso della copia, e un riferimento al buffer viene passato al chiamato. A meno che non si tratti di un **BSTR** allocato con **SysAllocString**, il riferimento viene sempre allocato con **CoTaskMemAlloc**.

Per ottimizzare il processo nel caso in cui il marshalling di uno dei tipi stringa venga eseguito per valore, come nel caso di una stringa di carattere Unicode, il gestore di marshalling passa al chiamato un puntatore diretto alle stringhe gestite nel buffer Unicode interno anziché copiarlo in uno nuovo.

> [!CAUTION]
> Quando una stringa viene passata per valore, il riferimento passato dal gestore di marshalling non deve mai essere modificato dal chiamato, per evitare danni all'heap gestito.

Quando un oggetto <xref:System.String?displayProperty=nameWithType> viene passato per riferimento, il contenuto della stringa viene copiato dal gestore di marshalling in un buffer secondario prima di effettuare la chiamata. Il contenuto del buffer viene quindi copiato in una nuova stringa dopo la chiamata. Grazie a questa tecnica, si garantisce che la stringa gestita immutabile rimanga inalterata.

Quando un oggetto <xref:System.Text.StringBuilder?displayProperty=nameWithType> viene passato per valore, un riferimento al buffer interno di **StringBuilder** viene passato dal gestore di marshalling direttamente al chiamante. Il chiamante e il chiamato devono concordare sulla dimensione del buffer. Il chiamante è responsabile della creazione di uno **StringBuilder** di lunghezza adeguata. Il chiamato deve prendere le precauzioni necessarie per garantire che il buffer non risulti sovraccarico. **StringBuilder** è un'eccezione alla regola in base alla quale i tipi di riferimento passati per valore vengono passati come parametri In per impostazione predefinita, dato che viene sempre passato come parametro In/Out.

## <a name="see-also"></a>Vedere anche

- [Comportamento di marshalling predefinito](default-marshaling-behavior.md)
- [Attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Marshalling di interoperabilità](interop-marshaling.md)
