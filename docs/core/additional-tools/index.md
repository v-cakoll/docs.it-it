---
title: Strumenti aggiuntivi
description: Panoramica degli strumenti aggiuntivi che è possibile installare e che supportano ed estendono la funzionalità di .NET Core.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: c0224a1cc6cbb9ae6fa88e5f869c47a1e84289e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77451525"
---
# <a name="net-core-additional-tools-overview"></a>Panoramica degli strumenti aggiuntivi per .NET Core

In questa sezione viene compilato un elenco di strumenti che supportano ed estendono la funzionalità .NET Core, oltre all'interfaccia della riga di comando di .NET Core.

## <a name="net-core-uninstall-tool"></a>Strumento di disinstallazione di .NET Core

Lo strumento di [disinstallazione](https://github.com/dotnet/cli-lab/releases) di .NET Core (`dotnet-core-uninstall`) consente di pulire gli SDK e i runtime di .NET Core in un sistema in modo che rimangano solo le versioni specificate. È disponibile una raccolta di opzioni per specificare quali versioni vengono disinstallate.

## <a name="net-core-diagnostic-tools"></a>Strumenti di diagnostica .NET Core

[dotnet-counters](../diagnostics/dotnet-counters.md) è uno strumento di monitoraggio delle prestazioni per il monitoraggio dello stato di primo livello e l'analisi delle prestazioni.dotnet-counters is a performance monitoring tool for first-level health monitoring and performance investigation.

[dotnet-dump](../diagnostics/dotnet-dump.md) fornisce un modo per raccogliere e analizzare i dump principali di Windows e Linux senza un debugger nativo.

[dotnet-trace](../diagnostics/dotnet-trace.md) raccoglie dati di profilatura dalla tua app che possono essere utili in scenari in cui devi scoprire cosa causa un rallentamento dell'esecuzione di un'app.

## <a name="wcf-web-service-reference-tool"></a>Strumento di riferimento al servizio Web WCFWCF Web Service Reference tool

Lo strumento di [riferimento del servizio Web](wcf-web-service-reference-guide.md) WCF (Windows Communication Foundation) è un provider di servizi connessi a Visual Studio che ha fatto il suo debutto in Visual Studio [2017 versione 15.5.](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools) Questo strumento recupera i metadati da un servizio Web nella soluzione corrente, in un percorso di rete o da un file WSDL. Genera un file di origine compatibile con .NET Core, definendo una classe proxy WCF con metodi che è possibile utilizzare per accedere alle operazioni del servizio Web.

## <a name="wcf-dotnet-svcutil-tool"></a>Strumento WCF dotnet-svcutil

Lo [strumento WCF dotnet-svcutil](dotnet-svcutil-guide.md) è uno strumento .NET che recupera i metadati da un servizio Web in un percorso di rete o da un file WSDL. Genera un file di origine compatibile con .NET Core, definendo una classe proxy WCF con metodi che è possibile utilizzare per accedere alle operazioni del servizio Web.

Lo strumento **dotnet-svcutil** è un'alternativa al provider di servizi connessi a Visual Studio di riferimento al [**servizio Web WCF,**](wcf-web-service-reference-guide.md) fornito per la prima volta con Visual Studio 2017 versione 15.5. Lo strumento **dotnet-svcutil,** come strumento .NET, è disponibile su Linux, macOS e Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a>Strumento dotnet-svcutil.xmlserializer WCF

In .NET Framework è possibile pregenerare un assembly di serializzazione usando lo strumento svcutil. Lo strumento WCF dotnet-svcutil.xmlserializer fornisce funzionalità simili in .NET Core.The WCF [dotnet-svcutil.xmlserializer tool](dotnet-svcutil.xmlserializer-guide.md) provides similar functionality on .NET Core. Pregenera il codice di serializzazione C# per i tipi dell'applicazione client che vengono usati dal contratto di servizio WCF e possono essere serializzati da <xref:System.Xml.Serialization.XmlSerializer>. Ciò migliora le prestazioni di avvio della serializzazione XML durante la serializzazione o la deserializzazione di oggetti di tali tipi.

## <a name="xml-serializer-generator"></a>Generazione serializzatore XML

Come il [Generatore di serializzatori Xml (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) per .NET Framework, il [pacchetto Microsoft.XmlSerializer.Generator NuGet](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione per le librerie .NET Core e .NET Standard. Crea un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.
