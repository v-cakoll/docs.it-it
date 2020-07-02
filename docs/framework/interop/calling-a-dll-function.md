---
title: Chiamata a una funzione di DLL
description: Esaminare i problemi relativi alla chiamata a una funzione di DLL che può sembrare confusa. Il processo chiamante della funzione è diverso a seconda che il tipo restituito sia copiabile.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 90f8f47148e652a9942a35be1564bed94c155216
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620898"
---
# <a name="calling-a-dll-function"></a>Chiamata a una funzione di DLL
Anche se le chiamate a funzioni di DLL non gestite sono quasi identiche alle chiamate ad altro codice gestito, esistono alcune differenze che possono rendere apparentemente poco chiaro l'uso delle funzioni di DLL. In questa sezione vengono presentati argomenti che descrivono alcuni aspetti meno comuni delle chiamate.  
  
 Le strutture che vengono restituite dalle chiamate platform invoke devono essere tipi di dati contenenti la stessa rappresentazione in codice gestito e non gestito. Questi tipi sono definiti *tipi copiabili da BLT* perché non richiedono la conversione. Vedere [Tipi copiabili e non copiabili da BLT](blittable-and-non-blittable-types.md). Per chiamare una funzione con una struttura non copiabile da BLT come tipo restituito, è possibile definire un tipo di helper copiabile da BLT della stessa dimensione del tipo non copiabile da BLT e convertire i dati dopo la restituzione della funzione.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Passaggio di strutture](passing-structures.md)  
 Identifica le problematiche relative al passaggio di strutture di dati con un layout predefinito.  
  
 [Funzioni di callback](callback-functions.md)  
 Include informazioni di base sulle funzioni di callback.  
  
 [Procedura: Implementare funzioni di callback](how-to-implement-callback-functions.md)  
 Descrive come implementare funzioni di callback nel codice gestito.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Utilizzo di funzioni di DLL non gestite](consuming-unmanaged-dll-functions.md)  
 Descrive come chiamare funzioni di DLL non gestite con platform invoke.  
  
 [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md)  
 Descrive come dichiarare i parametri dei metodi e passare gli argomenti alle funzioni esportate dalle librerie non gestite.
