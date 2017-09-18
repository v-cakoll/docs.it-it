---
title: "Interoperabilità con codice non gestito"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ff86b062efddde6f97555efb97247f60a6e1db98
ms.contentlocale: it-it
ms.lasthandoff: 09/18/2017

---
# <a name="interoperating-with-unmanaged-code"></a>Interoperabilità con codice non gestito
.NET Framework favorisce l'interazione con componenti COM, servizi COM+, librerie dei tipi esterne e molti servizi del sistema operativo. I tipi di dati, le firme dei metodi e i meccanismi di gestione degli errori variano tra modelli a oggetti gestiti e non gestiti. Per semplificare l'interoperabilità tra componenti .NET Framework e codice non gestito e agevolare il percorso di migrazione, Common Language Runtime nasconde ai client e ai server le differenze di questi modelli a oggetti.  
  
 Il codice eseguito sotto il controllo del runtime viene definito codice gestito. Al contrario, il codice eseguito esternamente al runtime viene definito codice non gestito. Esempi di codice non gestito sono i componenti COM, le interfacce ActiveX e le funzioni dell'API Win32.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Argomenti sulle procedure di interoperabilità con codice non gestito](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 Fornisce i collegamenti a tutte le procedure contenute nella documentazione sui concetti relativi all'interoperabilità con codice non gestito.  
  
 [Esposizione di componenti COM a .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 Descrive come usare componenti COM da applicazioni .NET Framework.  
  
 [Esposizione di componenti .NET Framework a COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Descrive come usare componenti .NET Framework da applicazioni COM.  
  
 [Utilizzo di funzioni di DLL non gestite](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Descrive come chiamare funzioni di DLL non gestite con platform invoke.  
  
 [Considerazioni di progettazione per l'interoperabilità](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 Fornisce suggerimenti per la scrittura di componenti COM integrati.  
  
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)  
 Descrive il marshalling per l'interoperabilità COM e platform invoke.  
  
 [Procedura: Eseguire il mapping di HRESULT ed eccezioni](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 Descrive il mapping tra eccezioni e valori HRESULT.  
  
 [Interoperabilità tramite tipi generici](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Descrive il comportamento dei tipi generici quando vengono usati nell'interoperabilità COM.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interoperabilità COM avanzata](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Contiene collegamenti per accedere ad altre informazioni sull'inclusione di componenti COM nell'applicazione .NET Framework.

