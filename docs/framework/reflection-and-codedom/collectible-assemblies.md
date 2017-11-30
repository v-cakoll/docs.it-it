---
title: Assembly ritirabili per la generazione di tipo dinamico
description: 
ms.date: 08/29/2017
ms.prod: .net
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c9a613f4cc13c3e4189a59ace2e05d01d1bcb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a>Assembly ritirabili per la generazione di tipo dinamico

*Assembly ritirabili* sono gli assembly dinamici che possono essere scaricati senza scaricare il dominio applicazione in cui sono stati creati. È possibile recuperare tutti i memoria gestita e utilizzato da un assembly ritirabile e i tipi che contiene. Informazioni quali il nome dell'assembly viene rimosso dalle tabelle interne.

Per abilitare lo scaricamento, utilizzare il <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> flag quando si crea un assembly dinamico. L'assembly è temporaneo (ovvero, non è possibile salvarlo) ed è soggetto alle limitazioni descritte nella [limitazioni degli assembly ritirabili](#restrictions-on-collectible-assemblies) sezione. Quando si rilasciano tutti gli oggetti associati all'assembly, common language runtime (CLR) Scarica automaticamente un assembly ritirabile. Tutti gli altri aspetti degli assembly ritirabili vengono creati e utilizzati nello stesso modo degli altri assembly dinamici.

## <a name="lifetime-of-collectible-assemblies"></a>Durata degli assembly ritirabili

La durata di un assembly ritirabile è controllata dall'esistenza di riferimenti a tipi che contiene e gli oggetti creati da tali tipi. Common language runtime non viene scaricato un assembly come uno o più dei seguenti esistono (`T` è qualsiasi tipo che viene definito nell'assembly): 

- Istanza di `T`.

- Un'istanza di una matrice di `T`.
 
- Un'istanza di un tipo generico che ha `T` come uno dei relativi argomenti di tipo. Ciò include le raccolte generiche di `T`, anche se tale raccolta è vuota.

- Un'istanza di <xref:System.Type> o <xref:System.Reflection.Emit.TypeBuilder> che rappresenta `T`. 

   > [!IMPORTANT]
   > È necessario rilasciare tutti gli oggetti che rappresentano parti dell'assembly. Il <xref:System.Reflection.Emit.ModuleBuilder> che definisce `T` mantiene un riferimento al <xref:System.Reflection.Emit.TypeBuilder>e <xref:System.Reflection.Emit.AssemblyBuilder> oggetto mantiene un riferimento al <xref:System.Reflection.Emit.ModuleBuilder>, pertanto è necessario rilasciare i riferimenti a questi oggetti. Anche l'esistenza di un <xref:System.Reflection.Emit.LocalBuilder> o <xref:System.Reflection.Emit.ILGenerator> utilizzata nella costruzione di `T` impedisce lo scaricamento.

- Un riferimento statico a `T` da un altro tipo definito in modo dinamico `T1` che è ancora raggiungibile mediante l'esecuzione del codice. Ad esempio, `T1` possono derivare da `T`, o `T` potrebbe essere il tipo di un parametro in un metodo di `T1`.
 
- Oggetto **ByRef** a un campo statico a cui appartiene `T`.

- Oggetto <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, o <xref:System.RuntimeMethodHandle> che fa riferimento a `T` o a un componente di `T`.

- Un'istanza di qualsiasi oggetto di reflection che può essere utilizzata indirettamente o direttamente per accedere il <xref:System.Type> oggetto che rappresenta `T`. Ad esempio, il <xref:System.Type> oggetto `T` può essere ottenuto da un tipo di matrice il cui tipo di elemento è `T`, o da un tipo generico che ha `T` come argomento di tipo. 

- Un metodo `M` nello stack di chiamate di un thread qualsiasi, in cui `M` è un metodo di `T` o un metodo a livello di modulo che viene definito nell'assembly.

- Un delegato a un metodo statico è definito in un modulo dell'assembly.

Se un elemento dall'elenco esiste solo per un solo tipo o di un metodo nell'assembly, il runtime non è possibile scaricare l'assembly.

> [!NOTE]
> Il runtime non scarica l'assembly fino a quando non sono eseguiti i finalizzatori per tutti gli elementi nell'elenco.

Per tener traccia della durata, un tipo generico costruito, ad esempio `List<int>` (in c#) o `List(Of Integer)` (in Visual Basic) che viene creata e utilizzata viene considerata la generazione di un assembly ritirabile sono stati definiti nell'assembly che contiene il tipo generico definizione del tipo o in un assembly che contiene la definizione di uno dei relativi argomenti di tipo. L'assembly esatto utilizzato è un dettaglio di implementazione e soggette a modifiche.
 
## <a name="restrictions-on-collectible-assemblies"></a>Limitazioni degli assembly ritirabili

Le restrizioni seguenti si applicano agli assembly ritirabile: 

- **Riferimenti statici**   
  Tipi in un assembly dinamico comune non possono avere riferimenti statici a tipi definiti in un assembly ritirabile. Se si definisce un tipo comune che eredita da un tipo in un assembly ritirabile, ad esempio un <xref:System.NotSupportedException> viene generata un'eccezione. Un tipo in un assembly ritirabile può avere riferimenti statici a un tipo in un altro assembly ritirabile, ma estende la durata dell'assembly di riferimento per la durata dell'assembly di riferimento.

- **Interoperabilità COM**   
   Nessuna interfaccia COM può essere definita all'interno di un assembly ritirabile e non le istanze di tipi all'interno di un assembly ritirabile possono essere convertite in oggetti COM. Un tipo in un assembly ritirabile non può fungere da un COM callable wrapper (CCW) o di un runtime callable wrapper (RCW). Tuttavia, tipi negli assembly ritirabili possono utilizzare gli oggetti che implementano le interfacce COM.

- **PInvoke**   
   Metodi che presentano il <xref:System.Runtime.InteropServices.DllImportAttribute> attributo non verrà compilato quando vengono dichiarati in un assembly ritirabile. Il <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> istruzione non può essere utilizzata nell'implementazione di un tipo in un assembly ritirabile e tali tipi non è possibile effettuare il marshalling a codice non gestito. Tuttavia, è possibile chiamare codice nativo usando un punto di ingresso che è dichiarato in un assembly non ritirabile.
 
- **Marshalling**   
   Impossibile effettuare il marshalling di oggetti (in particolare, delegati) che vengono definiti negli assembly ritirabile. Si tratta di una restrizione per tutti i tipi generati temporanei.

- **Caricamento di assembly**   
   La reflection emit è l'unico meccanismo supportato per il caricamento degli assembly ritirabili. Gli assembly caricati con qualsiasi altra forma di caricamenti di assembly non possono essere scaricati.
 
- **Oggetti associati al contesto**    
   Le variabili di contesto statico non sono supportate. Non è possibile estendere i tipi in un assembly ritirabile <xref:System.ContextBoundObject>. Tuttavia, codice negli assembly ritirabili può utilizzare gli oggetti associati al contesto definiti altrove.

- **Dati statici thread**       
   Le variabili statiche di thread non sono supportate.

## <a name="see-also"></a>Vedere anche

[Creazione di assembly e metodi dinamici](emitting-dynamic-methods-and-assemblies.md)
