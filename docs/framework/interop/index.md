---
title: "Interoperabilità con codice non gestito"
ms.date: 01/17/2018
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38c569633304ed9e6f86e7a04ef7b0dfa79b6704
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="interoperating-with-unmanaged-code"></a>Interoperabilità con codice non gestito

.NET Framework favorisce l'interazione con componenti COM, servizi COM+, librerie dei tipi esterne e molti servizi del sistema operativo. I tipi di dati, le firme dei metodi e i meccanismi di gestione degli errori variano tra modelli a oggetti gestiti e non gestiti. Per semplificare l'interoperabilità tra componenti .NET Framework e codice non gestito e agevolare il percorso di migrazione, Common Language Runtime nasconde ai client e ai server le differenze di questi modelli a oggetti.

Il codice eseguito sotto il controllo del runtime viene definito codice gestito. Al contrario, il codice eseguito esternamente al runtime viene definito codice non gestito. Esempi di codice non gestito sono i componenti COM, le interfacce ActiveX e le funzioni dell'API Win32.

## <a name="in-this-section"></a>Contenuto della sezione

[Esposizione di componenti COM a .NET Framework](exposing-com-components.md)  
Descrive come usare componenti COM da applicazioni .NET Framework.

[Esposizione di componenti .NET Framework a COM](exposing-dotnet-components-to-com.md)  
Descrive come usare componenti .NET Framework da applicazioni COM.

[Utilizzo di funzioni di DLL non gestite](consuming-unmanaged-dll-functions.md)  
Descrive come chiamare funzioni di DLL non gestite con platform invoke.

[Marshalling di interoperabilità](interop-marshaling.md)  
Descrive il marshalling per l'interoperabilità COM e platform invoke.

[Procedura: Eseguire il mapping di HRESULT ed eccezioni](how-to-map-hresults-and-exceptions.md)  
Descrive il mapping tra eccezioni e valori HRESULT.

[Wrapper COM](com-wrappers.md)  
Descrive i wrapper forniti dall'interoperabilità COM.

[Equivalenza del tipo e tipi di interoperabilità incorporati](type-equivalence-and-embedded-interop-types.md)  
Descrive come informazioni sui tipi COM sono incorporate nell'assembly e come common language runtime determina l'equivalenza dei tipi COM incorporati.

[Procedura: generare assembly di interoperabilità tramite Tlbimp.exe](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
Viene descritto come generare assembly di interoperabilità primario utilizzando *Tlbimp.exe* (tipo di libreria utilità di importazione).

[Procedura: Registrare assembly di interoperabilità primari](how-to-register-primary-interop-assemblies.md)  
Viene descritto come registrare assembly di interoperabilità primari prima di potervi fare riferimento nei progetti.

[Interoperabilità COM senza registrazione](registration-free-com-interop.md)  
Descrive la modalità di interoperabilità COM attivazione componenti senza utilizzare il Registro di sistema di Windows.

[Procedura: Configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione](configure-net-framework-based-com-components-for-reg.md)  
Viene descritto come creare un manifesto dell'applicazione e come creare e incorporare un manifesto del componente.
