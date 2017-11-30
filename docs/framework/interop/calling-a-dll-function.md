---
title: Chiamata a una funzione di DLL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36f84796b9682411d7907cfc10d584d772ef00a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="calling-a-dll-function"></a>Chiamata a una funzione di DLL
Anche se le chiamate a funzioni di DLL non gestite sono quasi identiche alle chiamate ad altro codice gestito, esistono alcune differenze che possono rendere apparentemente poco chiaro l'uso delle funzioni di DLL. In questa sezione vengono presentati argomenti che descrivono alcuni aspetti meno comuni delle chiamate.  
  
 Le strutture che vengono restituite dalle chiamate platform invoke devono essere tipi di dati contenenti la stessa rappresentazione in codice gestito e non gestito. Questi tipi sono definiti *tipi copiabili da BLT* perché non richiedono la conversione. Vedere [Tipi copiabili e non copiabili da BLT](../../../docs/framework/interop/blittable-and-non-blittable-types.md). Per chiamare una funzione con una struttura non copiabile da BLT come tipo restituito, è possibile definire un tipo di helper copiabile da BLT della stessa dimensione del tipo non copiabile da BLT e convertire i dati dopo la restituzione della funzione.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Passaggio di strutture](../../../docs/framework/interop/passing-structures.md)  
 Identifica le problematiche relative al passaggio di strutture di dati con un layout predefinito.  
  
 [Funzioni di callback](../../../docs/framework/interop/callback-functions.md)  
 Include informazioni di base sulle funzioni di callback.  
  
 [Procedura: Implementare funzioni di callback](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 Descrive come implementare funzioni di callback nel codice gestito.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Utilizzo di funzioni di DLL non gestite](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Descrive come chiamare funzioni di DLL non gestite con platform invoke.  
  
 [Marshalling dei dati con platform invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 Descrive come dichiarare i parametri dei metodi e passare gli argomenti alle funzioni esportate dalle librerie non gestite.
