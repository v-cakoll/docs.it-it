---
title: Altri strumenti
description: Panoramica degli strumenti aggiuntivi che è possibile installare e che supportano ed estendono la funzionalità di .NET Core.
author: mlacouture
ms.date: 12/02/2019
ms.custom: mvc
ms.openlocfilehash: 23b94ceef729cdc3d83032e3897312eb1d1afd79
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920937"
---
# <a name="net-core-additional-tools-overview"></a>Panoramica degli strumenti aggiuntivi per .NET Core

Questa sezione compila un elenco di strumenti che supportano ed estendono le funzionalità di .NET Core, oltre ai interfaccia della riga di comando di .NET Core.

## <a name="net-core-uninstall-tooluninstall-toolmd"></a>[Strumento di disinstallazione di .NET Core](uninstall-tool.md)

Lo [strumento di disinstallazione di .NET Core](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) consente di pulire gli SDK e i Runtime .NET Core in un sistema in modo che rimangano solo le versioni specificate. È disponibile una raccolta di opzioni per specificare quali versioni vengono disinstallate.

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[Strumento WCF Web Service Reference](wcf-web-service-reference-guide.md)

WCF (Windows Communication Foundation) Web Service Reference è un provider di servizi connessi di Visual Studio disponibile per la prima volta con [Visual Studio 2017 versione 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools). Questo strumento consente di recuperare i metadati da un servizio Web nella soluzione corrente, in un percorso di rete o da un file WSDL. Genera un file di origine compatibile con .NET Core, definendo una classe proxy WCF con i metodi che è possibile usare per accedere alle operazioni del servizio Web.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[Strumento WCF dotnet-svcutil](dotnet-svcutil-guide.md)

Lo strumento DotNet-Svcutil WCF (Windows Communication Foundation) è uno strumento .NET che consente di recuperare metadati da un servizio Web in un percorso di rete o da un file WSDL. Genera un file di origine compatibile con .NET Core, definendo una classe proxy WCF con i metodi che è possibile usare per accedere alle operazioni del servizio Web.

Lo strumento **DotNet-Svcutil** è un'opzione alternativa al [**servizio Web WCF riferimento**](wcf-web-service-reference-guide.md) al provider di servizi connessi di Visual Studio, che è stato prima fornito con visual studio 2017 versione 15,5. Lo strumento **DotNet-Svcutil** , come strumento .NET, è disponibile su più piattaforme in Linux, MacOS e Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tooldotnet-svcutilxmlserializer-guidemd"></a>[Strumento dotnet-svcutil.xmlserializer WCF](dotnet-svcutil.xmlserializer-guide.md)

In .NET Framework è possibile pregenerare un assembly di serializzazione usando lo strumento svcutil. Il pacchetto NuGet dotnet-svcutil.xmlserializer fornisce funzionalità simili in .NET Core. Pregenera il codice di serializzazione C# per i tipi dell'applicazione client che vengono usati dal contratto di servizio WCF e possono essere serializzati da <xref:System.Xml.Serialization.XmlSerializer>. Ciò migliora le prestazioni di avvio della serializzazione XML durante la serializzazione o la deserializzazione di oggetti di tali tipi.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[Generazione serializzatore XML](xml-serializer-generator.md)

Come il [Generatore di serializzatori Xml (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) per .NET Framework, il [pacchetto Microsoft.XmlSerializer.Generator NuGet](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione per le librerie .NET Core e .NET Standard. Crea un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.
