---
title: Membri - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#], nested types
- C# language, type members
ms.assetid: 4a30a4ab-d690-4936-9124-92ce9448665a
ms.openlocfilehash: 09802431d0a5954b67687e9878f572541eeaac79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705509"
---
# <a name="members-c-programming-guide"></a>Membri (Guida per programmatori C#)

Le classi e gli struct contengono membri che ne rappresentano i dati e il comportamento. I membri di una classe includono tutti i membri dichiarati nella classe, oltre a tutti i membri (ad eccezione di costruttori e finalizzatori) dichiarati in tutte le classi nella relativa gerarchia di ereditarietà. I membri privati nelle classi base vengono ereditati ma non sono accessibili dalle classi derivate.  
  
 Nella tabella seguente sono elencati i tipi di membri che possono essere contenuti in una classe o in uno struct:  
  
|Membro|Descrizione|  
|------------|-----------------|  
|[Campi](./fields.md)|I campi sono variabili dichiarate nell'ambito della classe. Un campo può essere un tipo numerico incorporato o un'istanza di un'altra classe. Una classe calendario può ad esempio avere un campo che contiene la data corrente.|  
|[Costanti](./constants.md)|Le costanti sono campi il cui valore è impostato in fase di compilazione e non può essere modificato.|  
|[Proprietà](./properties.md)|Le proprietà sono metodi di una classe ai quali si accede come se si trattasse di campi della classe. Possono garantire la sicurezza di un campo di una classe in modo da impedire che venga modificato all'insaputa dell'oggetto.|  
|[Metodi](./methods.md)|I metodi definiscono le azioni che una classe è in grado di eseguire. Possono accettare parametri che forniscono dati di input e restituire dati di output tramite i parametri. Possono anche restituire un valore direttamente, senza l'uso di parametri.|  
|[Events](../events/index.md)|Gli eventi forniscono notifiche ad altri oggetti su ciò che si verifica, ad esempio le operazioni di clic su pulsanti o il completamento corretto di un metodo. Vengono definiti e generati tramite i delegati.|  
|[Operatori](../../language-reference/operators/index.md)|Gli operatori sottoposti a overload sono considerati membri del tipo. Quando si esegue l'overload di un operatore, lo si definisce come metodo statico pubblico in un tipo. Per altre informazioni, vedere [Overload degli operatori](../../language-reference/operators/operator-overloading.md).|  
|[Indicizzatori](../indexers/index.md)|Gli indicizzatori consentono di eseguire l'indicizzazione di un oggetto in modo simile a quanto avviene per le matrici.|  
|[Costruttori](./constructors.md)|I costruttori sono metodi che vengono chiamati la prima volta che viene creato l'oggetto. Vengono spesso usati per inizializzare i dati di un oggetto.|  
|[Finalizzatori](./destructors.md)|I finalizzatori vengono usati molto raramente in C#. Questi sono metodi che vengono chiamati dal motore di esecuzione di runtime quando l'oggetto sta per essere rimosso dalla memoria. Vengono in genere usati per assicurarsi che le eventuali risorse da rilasciare vengano gestite nel modo appropriato.|  
|[Tipi annidatiNested Types](./nested-types.md)|I tipi nidificati sono tipi dichiarati all'interno di un altro tipo. Vengono spesso usati per descrivere gli oggetti usati solo dai tipi che li contengono.|  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi](./classes.md)
