---
title: Concetti relativi alla serializzazione
ms.date: 08/07/2017
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
ms.openlocfilehash: f16de0e95f7520e377dc9920743261ad6019e430
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-concepts"></a>Concetti relativi alla serializzazione
Perché utilizzare la serializzazione? I due motivi principali sono la possibilità di rendere persistente lo stato di un oggetto su un supporto di archiviazione in modo da potere ricreare una copia esatta in una fase successiva e di inviare l'oggetto per valore da un dominio dell'applicazione a un altro. Ad esempio, la serializzazione viene utilizzata per salvare lo stato della sessione in ASP.NET e per copiare oggetti negli Appunti in Windows Form. Viene inoltre utilizzata da .NET Remoting per passare oggetti per valore da un dominio dell'applicazione a un altro.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="persistent-storage"></a>Archiviazione permanente
Spesso risulta necessario archiviare il valore dei campi di un oggetto su disco e in un secondo momento recuperare tali dati. Sebbene ciò sia facilmente realizzabile senza basarsi sulla serializzazione, questo approccio è spesso scomodo e tendente all'errore e diviene sempre più complesso quando è necessario registrare una gerarchia di oggetti. Si provi a immaginare di dovere scrivere un'applicazione aziendale di grandi dimensioni contenente migliaia di oggetti e di dovere scrivere codice per salvare e ripristinare i campi e le proprietà su e da disco per ogni oggetto. La serializzazione fornisce un comodo meccanismo per raggiungere tale obiettivo.

Common Language Runtime gestisce il modo in cui gli oggetti vengono archiviati in memoria e fornisce un meccanismo di serializzazione automatizzato tramite l'uso della [reflection](../../../docs/framework/reflection-and-codedom/reflection.md). Quando un oggetto viene serializzato, il nome della classe, l'assembly e tutti i membri dati dell'istanza della classe vengono scritti nell'archiviazione. Gli oggetti spesso archiviano riferimenti ad altre istanze nelle variabili membro. Quando la classe viene serializzata, il motore di serializzazione registra oggetti a cui viene fatto riferimento, già serializzati, in modo da assicurare che lo stesso oggetto non venga serializzato più volte. L'architettura di serializzazione fornita con il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] gestisce correttamente e automaticamente gli oggetti grafici e i riferimenti circolari. L'unico requisito a cui devono attenersi gli oggetti grafici è che tutti gli oggetti, a cui viene fatto riferimento dall'oggetto serializzato, devono essere anche contrassegnati come `Serializable` (per altre informazioni, vedere [Serializzazione di base](basic-serialization.md)). Se ciò non viene fatto, viene generata un'eccezione nel momento in cui il serializzatore tenta di serializzare l'oggetto non contrassegnato.

Quando la classe serializzata viene deserializzata, la classe viene ricreata e i valori di tutti i membri dati vengono ripristinati automaticamente.

## <a name="marshal-by-value"></a>Marshalling in base al valore
Gli oggetti sono validi solo nel dominio dell'applicazione in cui sono stati creati. Qualsiasi tentativo di passare l'oggetto come parametro o restituirlo come risultato non avrà esito positivo, a meno che l'oggetto non derivi da `MarshalByRefObject` o sia contrassegnato come `Serializable`. Se l'oggetto è contrassegnato come `Serializable`, l'oggetto sarà serializzato automaticamente, verrà trasportato da un dominio dell'applicazione all'altro e sarà successivamente deserializzato in modo da produrre una copia esatta dell'oggetto nel secondo dominio dell'applicazione. Tale processo viene generalmente denominato marshalling in base al valore.
 
Quando un oggetto deriva da `MarshalByRefObject`, viene passato un riferimento all'oggetto da un dominio dell'applicazione a un altro e non l'oggetto stesso. È anche possibile contrassegnare un oggetto che deriva da `MarshalByRefObject` come `Serializable`. Se questo oggetto viene usato con i sevizi remoti, il formattatore responsabile della serializzazione, preconfigurato con un selettore di surrogati (`SurrogateSelector`), prende il controllo del processo di serializzazione e sostituisce tutti gli oggetti derivati da `MarshalByRefObject` con un proxy. Senza `SurrogateSelector`, invece, l'architettura della serializzazione segue le regole della serializzazione standard descritte in [Passaggi del processo di serializzazione](steps-in-the-serialization-process.md).  

## <a name="related-sections"></a>Sezioni correlate  
 [Serializzazione binaria](../../../docs/standard/serialization/binary-serialization.md)  
 Descrive il meccanismo della serializzazione binaria incluso nel Common Language Runtime.  
  
 [Oggetti remoti](https://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58)  
 Vengono descritti i diversi metodi di comunicazione disponibili in .NET Framework per le comunicazioni remote.  
  
 [Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 Descrive il meccanismo della serializzazione XML e SOAP incluso nel Common Language Runtime.
