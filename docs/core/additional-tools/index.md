---
title: Altri strumenti
description: Panoramica degli strumenti aggiuntivi che è possibile installare e che supportano ed estendono la funzionalità di .NET Core.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: c0224a1cc6cbb9ae6fa88e5f869c47a1e84289e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451525"
---
# <a name="net-core-additional-tools-overview"></a>Panoramica degli strumenti aggiuntivi per .NET Core

Questa sezione compila un elenco di strumenti che supportano ed estendono le funzionalità di .NET Core, oltre ai interfaccia della riga di comando di .NET Core.

## <a name="net-core-uninstall-tool"></a>Strumento di disinstallazione di .NET Core

Lo [strumento di disinstallazione di .NET Core](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) consente di pulire gli SDK e i Runtime .NET Core in un sistema in modo che rimangano solo le versioni specificate. È disponibile una raccolta di opzioni per specificare quali versioni vengono disinstallate.

## <a name="net-core-diagnostic-tools"></a>Strumenti di diagnostica .NET Core

[DotNet-Counters](../diagnostics/dotnet-counters.md) è uno strumento di monitoraggio delle prestazioni per il monitoraggio dell'integrità di primo livello e l'analisi delle prestazioni.

[DotNet-dump](../diagnostics/dotnet-dump.md) fornisce un modo per raccogliere e analizzare i dump di Windows e Linux core senza un debugger nativo.

[DotNet-Trace](../diagnostics/dotnet-trace.md) raccoglie i dati di profilatura dall'app che possono essere utili negli scenari in cui è necessario individuare la causa dell'esecuzione lenta di un'app.

## <a name="wcf-web-service-reference-tool"></a>Strumento di riferimento al servizio Web WCF

Lo strumento di riferimento al [servizio Web](wcf-web-service-reference-guide.md) WCF (Windows Communication Foundation) è un provider di servizi connessi di Visual Studio che ha eseguito il suo debutto in [Visual studio 2017 versione 15,5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools). Questo strumento consente di recuperare i metadati da un servizio Web nella soluzione corrente, in un percorso di rete o da un file WSDL. Genera un file di origine compatibile con .NET Core, definendo una classe proxy WCF con i metodi che è possibile usare per accedere alle operazioni del servizio Web.

## <a name="wcf-dotnet-svcutil-tool"></a>Strumento WCF DotNet-Svcutil

Lo [strumento WCF DotNet-Svcutil](dotnet-svcutil-guide.md) è uno strumento .NET che consente di recuperare metadati da un servizio Web in un percorso di rete o da un file WSDL. Genera un file di origine compatibile con .NET Core, definendo una classe proxy WCF con i metodi che è possibile usare per accedere alle operazioni del servizio Web.

Lo strumento **DotNet-Svcutil** è un'alternativa al [**servizio Web WCF riferimento**](wcf-web-service-reference-guide.md) al provider di servizi connessi di Visual Studio, che è stato prima fornito con visual studio 2017 versione 15,5. Lo strumento **DotNet-Svcutil** come strumento .NET è disponibile in Linux, MacOS e Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a>Strumento WCF DotNet-Svcutil. XmlSerializer

In .NET Framework è possibile pregenerare un assembly di serializzazione usando lo strumento svcutil. Lo [strumento WCF DotNet-Svcutil. XmlSerializer](dotnet-svcutil.xmlserializer-guide.md) fornisce funzionalità simili in .NET Core. Pregenera il codice di serializzazione C# per i tipi dell'applicazione client che vengono usati dal contratto di servizio WCF e possono essere serializzati da <xref:System.Xml.Serialization.XmlSerializer>. Ciò migliora le prestazioni di avvio della serializzazione XML durante la serializzazione o la deserializzazione di oggetti di tali tipi.

## <a name="xml-serializer-generator"></a>Generazione serializzatore XML

Come il [Generatore di serializzatori Xml (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) per .NET Framework, il [pacchetto Microsoft.XmlSerializer.Generator NuGet](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione per le librerie .NET Core e .NET Standard. Viene creato un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.
