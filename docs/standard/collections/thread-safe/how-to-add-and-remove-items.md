---
title: 'Procedura: aggiungere e rimuovere elementi da un oggetto ConcurrentDictionary'
description: Vedere un esempio di come aggiungere, recuperare, aggiornare e rimuovere elementi dalla classe ConcurrentDictionary<TKey, TValue> Collection in .NET.
ms.date: 05/04/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
ms.openlocfilehash: 827eb9db984289929c591046a4713419c9587312
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662862"
---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>Procedura: aggiungere e rimuovere elementi da un oggetto ConcurrentDictionary

In questo esempio viene illustrato come aggiungere, recuperare, aggiornare e rimuovere elementi da un oggetto <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>. Questa classe di raccolta è un'implementazione thread-safe. È consigliabile usarla ogni volta che più thread tentano di accedere contemporaneamente agli elementi.

<xref:System.Collections.Concurrent.ConcurrentDictionary%602> offre molti metodi pratici che consentono al codice di evitare il controllo dell'esistenza di una chiave prima di aggiungere o rimuovere dati. Nella tabella seguente vengono elencati questi metodi pratici e viene specificato quando usarli.

| Metodo | Casi di uso |
|--|--|
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> | Si vuole aggiungere un nuovo valore ad una chiave specificata e, se la chiave esiste già, si vuole sostituirne il valore. |
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> | Si vuole recuperare il valore esistente per una chiave specificata e, se la chiave non esiste, si vuole specificare una coppia chiave/valore. |
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A> | Si vuole aggiungere, ottenere, aggiornare o rimuovere una coppia chiave/valore e, se la chiave esiste già o il tentativo non riesce per qualsiasi altro motivo, si vuole eseguire un'azione alternativa. |

## <a name="example"></a>Esempio

Nell'esempio seguente vengono usate due istanze di <xref:System.Threading.Tasks.Task> per aggiungere contemporaneamente alcuni elementi a <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, quindi viene restituito tutto il contenuto per indicare che gli elementi sono stati aggiunti correttamente. Nell'esempio viene inoltre illustrato come utilizzare i <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> metodi, e <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> per aggiungere, aggiornare e recuperare elementi dalla raccolta.

[!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
[!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]

<xref:System.Collections.Concurrent.ConcurrentDictionary%602> è progettato per gli scenari multithreading. Non è necessario usare blocchi nel codice per aggiungere o rimuovere elementi dalla raccolta. Tuttavia, è sempre possibile per un thread recuperare un valore, e per un altro thread aggiornare immediatamente la raccolta assegnando un nuovo valore alla stessa chiave.

Sebbene tutti i metodi di <xref:System.Collections.Concurrent.ConcurrentDictionary%602> sono thread-safe, non tutti i metodi sono atomici, in particolare <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> e <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>. Il delegato utenti passato a questi metodi viene richiamato fuori dal blocco interno del dizionario (questa operazione viene eseguita per impedire a un codice sconosciuto di bloccare tutti i thread). Pertanto, è possibile che per questa sequenza di eventi si verifichi quanto segue:

1. _ThreadA_ chiama <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> , non trova alcun elemento e crea un nuovo elemento da aggiungere richiamando il `valueFactory` delegato.

1. _ThreadB_ chiama <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> contemporaneamente, il `valueFactory` delegato viene richiamato e arriva al blocco interno prima di _ThreadA_, quindi la nuova coppia chiave-valore viene aggiunta al dizionario.

1. il delegato utente _di threadA viene_ completato e il thread arriva al blocco, ma ora rileva che l'elemento esiste già.

1. _ThreadA_ esegue un'"Get" e restituisce i dati aggiunti precedentemente da _ThreadB_.

Pertanto, non è garantito che i dati restituiti da <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> corrispondano agli stessi dati creati dall'oggetto del thread `valueFactory` . Una sequenza di eventi simile può verificarsi quando viene chiamato <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Raccolte thread-safe](index.md)
