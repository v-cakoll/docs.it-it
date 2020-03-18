---
title: Campi - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
ms.openlocfilehash: 46d4f77a4a490b2acdb5da20b9a477f27c38d410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628241"
---
# <a name="fields-c-programming-guide"></a>Campi (Guida per programmatori C#)

Un *campo* è una variabile di qualsiasi tipo che viene dichiarata direttamente in una [classe](../../language-reference/keywords/class.md) o [struct](../../language-reference/builtin-types/struct.md). I campi sono *membri* del rispettivo tipo contenitore.

Una classe o uno struct può avere campi di istanza, campi statici o entrambi. I campi di istanza sono specifici di un'istanza di tipo. Se si ha una classe T con un campo di istanza F, è possibile creare due oggetti di tipo T e modificare il valore di F in ciascun oggetto senza modificare il valore nell'altro oggetto. Al contrario, un campo statico appartiene alla classe stessa ed è condiviso tra tutte le istanze della classe. È possibile accedere al campo statico solo utilizzando il nome della classe. Se si accede al campo statico tramite un nome di istanza, viene visualizzato un errore in fase di compilazione [CS0176.](../../misc/cs0176.md)

In genere è necessario usare i campi solo per le variabili che hanno accesso privato o protetto. I dati esposti dalla classe al codice client devono essere forniti tramite [metodi,](./methods.md) [proprietà](./properties.md)e [indicizzatori.](../indexers/index.md) Usando questi costrutti per l'accesso indiretto ai campi interni, è possibile evitare valori di input non validi. Un campo privato che archivia i dati esposti da una proprietà pubblica è chiamato *archivio di backup* o *campo sottostante*.

Di solito i campi archiviano dati che devono essere accessibili a più metodi della classe e devono essere archiviati per un tempo maggiore rispetto alla durata di ogni singolo metodo. Ad esempio, una classe che rappresenta una data di calendario potrebbe contenere tre campi interi: uno per il mese, uno per il giorno e uno per l'anno. Le variabili che vengono usate solo all'interno dell'ambito di un singolo metodo devono essere dichiarate come *variabili locali* all'interno del corpo del metodo stesso.

I campi vengono dichiarati nel blocco della classe, specificando il livello di accesso del campo, seguito dal tipo di campo e poi dal nome del campo. Ad esempio:

[!code-csharp[csProgGuideObjects#61](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#61)]

Per accedere a un campo in un oggetto, aggiungere un punto dopo il nome dell'oggetto, seguito dal nome del campo, come in `objectname.fieldname`. Ad esempio:

[!code-csharp[csProgGuideObjects#62](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#62)]

È possibile assegnare a un campo un valore iniziale usando l'operatore di assegnazione quando il campo viene dichiarato. Per assegnare automaticamente il campo `day` a `"Monday"`, ad esempio, è necessario dichiarare `day` come nell'esempio seguente:

[!code-csharp[csProgGuideObjects#63](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#63)]

I campi vengono inizializzati immediatamente prima della chiamata del costruttore per l'istanza dell'oggetto. Se il costruttore assegna il valore di un campo, sovrascriverà qualsiasi valore assegnato nella dichiarazione del campo. Per altre informazioni, vedere [Uso dei costruttori](./using-constructors.md).

> [!NOTE]
> Un inizializzatore di campo non può fare riferimento ad altri campi di istanza.

I campi possono essere contrassegnati come [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md)o private [protected](../../language-reference/keywords/private-protected.md). Questi modificatori di accesso definiscono in che modo gli utenti della classe possono accedere ai campi. Per altre informazioni, vedere [Modificatori di accesso](./access-modifiers.md).

È possibile facoltativamente dichiarare un campo come [static](../../language-reference/keywords/static.md). Questo rende il campo disponibile per i chiamanti in qualsiasi momento, anche se non esiste alcuna istanza della classe. Per ulteriori informazioni, vedere [Classi statiche e Membri di classi statiche](./static-classes-and-static-class-members.md).

È possibile dichiarare un campo come [readonly](../../language-reference/keywords/readonly.md). A un campo di sola lettura può essere assegnato un valore solo durante l'inizializzazione o in un costruttore. Un campo `static readonly` è molto simile a una costante, a parte il fatto che il compilatore C# non ha accesso al valore di un campo statico di sola lettura in fase di compilazione, ma solo in fase di esecuzione. Per altre informazioni, vedere [Costanti](./constants.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Uso dei costruttori](./using-constructors.md)
- [Ereditarietà](./inheritance.md)
- [Modificatori di accesso](./access-modifiers.md)
- [Classi e membri delle classi astratte e sealed](./abstract-and-sealed-classes-and-class-members.md)
