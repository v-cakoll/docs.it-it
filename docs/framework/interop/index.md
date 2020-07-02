---
title: Interoperabilità con codice non gestito
description: Verificare l'interoperabilità con codice non gestito. CLR si nasconde dai client e dai server in base alla differenza tra i modelli a oggetti dei componenti .NET e il codice non gestito.
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 1cebd75907fd202715cb337593186d248107bdbb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621873"
---
# <a name="interoperating-with-unmanaged-code"></a>Interoperabilità con codice non gestito

.NET Framework favorisce l'interazione con componenti COM, servizi COM+, librerie dei tipi esterne e molti servizi del sistema operativo. I tipi di dati, le firme dei metodi e i meccanismi di gestione degli errori variano tra modelli a oggetti gestiti e non gestiti. Per semplificare l'interoperabilità tra componenti .NET Framework e codice non gestito e agevolare il percorso di migrazione, Common Language Runtime nasconde ai client e ai server le differenze di questi modelli a oggetti.

Il codice eseguito sotto il controllo del runtime viene definito codice gestito. Al contrario, il codice eseguito esternamente al runtime viene definito codice non gestito. Esempi di codice non gestito sono i componenti COM, le interfacce ActiveX e le funzioni dell'API Windows.

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

[Equivalenza del tipo e tipi di interoperabilità incorporati](type-equivalence-and-embedded-interop-types.md)  
Descrive il modo in cui le informazioni sui tipi COM sono incorporate negli assembly e come Common Language Runtime determina l'equivalenza dei tipi COM incorporati.

[Procedura: Generare assembly di interoperabilità primari tramite Tlbimp.exe](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
Descrive come generare assembly di interoperabilità primari usando *Tlbimp.exe* (strumento di importazione di librerie dei tipi).

[Procedura: Registrare assembly di interoperabilità primari](how-to-register-primary-interop-assemblies.md)  
Descrive come registrare gli assembly di interoperabilità primari prima di potervi fare riferimento nei progetti.

[Interoperabilità COM senza registrazione](registration-free-com-interop.md)  
Descrive come l'interoperabilità COM consente di attivare componenti senza usare il Registro di sistema di Windows.

[Procedura: Configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione](configure-net-framework-based-com-components-for-reg.md)  
Descrive come creare un manifesto dell'applicazione e come creare e incorporare un manifesto del componente.

## <a name="related-sections"></a>Sezioni correlate

[Wrapper COM](../../standard/native-interop/com-wrappers.md)  
Descrive i wrapper forniti dall'interoperabilità COM.
