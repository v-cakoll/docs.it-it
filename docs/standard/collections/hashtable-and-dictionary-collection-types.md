---
title: Tipi di Collection Hashtable e Dictionary
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Hashtable class, grouping data in collections
- Hashtable collection type
- hash tables
- grouping data in collections, Hashtable collection type
- hash function
- collections [.NET Framework], Hashtable collection type
ms.assetid: bfc20837-3d02-4fc7-8a8f-c5215b6b7913
ms.openlocfilehash: a6f234b6205fd30507b9342d9839db6adcddfc2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711376"
---
# <a name="hashtable-and-dictionary-collection-types"></a>Tipi di Collection Hashtable e Dictionary
La classe <xref:System.Collections.Hashtable?displayProperty=nameWithType> e le classi generiche <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> e <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> implementano l'interfaccia <xref:System.Collections.IDictionary?displayProperty=nameWithType>. La classe generica <xref:System.Collections.Generic.Dictionary%602> implementa inoltre l'interfaccia generica <xref:System.Collections.Generic.IDictionary%602>. Ogni elemento di queste raccolte è pertanto una coppia chiave-valore.  
  
 Un oggetto <xref:System.Collections.Hashtable> è costituito da bucket che contengono gli elementi della raccolta. Un bucket è un sottogruppo virtuale di elementi all'interno di <xref:System.Collections.Hashtable>, che rende più semplici e veloci le operazioni di ricerca e recupero rispetto alla maggior parte delle raccolte. Ogni bucket è associato a un codice hash, generato usando una funzione hash ed basato sulla chiave dell'elemento.  
  
 La classe generica <xref:System.Collections.Generic.HashSet%601> è una raccolta non ordinata destinata a contenere elementi univoci.  
  
 Una funzione hash è un algoritmo che restituisce un codice hash numerico basato su una chiave. La chiave è il valore di una proprietà dell'oggetto che viene archiviato. Una funzione hash deve sempre restituire lo stesso codice hash per la stessa chiave. È possibile per una funzione hash generare lo stesso codice hash per due chiavi diverse, ma una funzione hash che genera un codice hash univoco per ogni chiave univoca offre prestazioni migliori durante il recupero di elementi dalla tabella hash.  
  
 Ogni oggetto usato come elemento in un oggetto <xref:System.Collections.Hashtable> deve essere in grado di generare un codice hash per se stesso tramite un'implementazione del metodo <xref:System.Object.GetHashCode%2A>. È tuttavia anche possibile specificare una funzione hash per tutti gli elementi in un oggetto <xref:System.Collections.Hashtable> usando un costruttore <xref:System.Collections.Hashtable> che accetta un'implementazione di <xref:System.Collections.IHashCodeProvider> come uno dei parametri.  
  
 Quando un oggetto viene aggiunto a <xref:System.Collections.Hashtable>, viene archiviato nel bucket associato al codice hash corrispondente al codice hash dell'oggetto. Quando viene cercato un valore in <xref:System.Collections.Hashtable>, viene generato il codice hash per tale valore e viene eseguita la ricerca nel bucket associato a tale codice hash.  
  
 Ad esempio, una funzione hash per una stringa potrebbe prendere i codici ASCII di ogni carattere della stringa e combinarli per generare un codice hash. La stringa "picnic" avrebbe un codice hash diverso da quello della stringa "basket", pertanto le due stringhe si troverebbero in bucket diversi. "Stressed" e "desserts" avrebbero invece lo stesso codice hash e si troverebbero nello stesso bucket.  
  
 Le classi <xref:System.Collections.Generic.Dictionary%602> e <xref:System.Collections.Concurrent.ConcurrentDictionary%602> hanno la stessa funzionalità della classe <xref:System.Collections.Hashtable>. Un oggetto <xref:System.Collections.Generic.Dictionary%602> di un tipo specifico (diverso da <xref:System.Object>) offre prestazioni migliori rispetto a un oggetto <xref:System.Collections.Hashtable> per i tipi di valore, in quanto gli elementi di <xref:System.Collections.Hashtable> sono di tipo <xref:System.Object>. Le conversioni boxing e unboxing vengono in genere eseguite quando si archivia o si recupera un tipo di valore. La classe <xref:System.Collections.Concurrent.ConcurrentDictionary%602> deve essere usata quando più thread potrebbero accedere contemporaneamente alla raccolta.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IDictionary>
- <xref:System.Collections.IHashCodeProvider>
- <xref:System.Collections.Generic.Dictionary%602>
- <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>
- [Tipi di Collection comunemente utilizzate](../../../docs/standard/collections/commonly-used-collection-types.md)
