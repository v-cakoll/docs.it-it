---
title: Estensione di metadati mediante attributi
description: Informazioni su come estendere i metadati usando gli attributi in .NET. Gli attributi sono dichiarazioni descrittive simili a parole chiave per aggiungere annotazioni a elementi di programmazione, ad esempio tipi e campi.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- metadata, extending
- attributes [.NET Framework], metadata
- elements [.NET Framework], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
ms.openlocfilehash: c77de970c5550bd896e83854414592d70eb9dc48
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598632"
---
# <a name="extending-metadata-using-attributes"></a>Estensione di metadati mediante attributi
Common Language Runtime consente di aggiungere dichiarazioni descrittive simili a parole chiave, dette attributi, per annotare gli elementi di programmazione quali tipi, campi, metodi e proprietà. Quando si compila il codice per il runtime, viene convertito in Microsoft Intermediate Language (MSIL) e inserito in un file eseguibile portabile (PE) insieme ai metadati generati dal compilatore. Gli attributi consentono di inserire informazioni descrittive aggiuntive nei metadati che possono essere estratte mediante i servizi di reflection di runtime. Il compilatore crea attributi quando si dichiarano istanze di classi speciali che derivano da <xref:System.Attribute?displayProperty=nameWithType>.  
  
 .NET Framework usa gli attributi per diversi motivi e per risolvere una vasta gamma di problemi. Gli attributi descrivono come serializzare i dati, specificare le caratteristiche che consentono di applicare la protezione e limitare le ottimizzazioni effettuate dal compilatore just-in-time (JIT) per facilitare il debug del codice. Gli attributi possono anche registrare il nome di un file o l'autore di codice o controllare la visibilità dei controlli e membri durante lo sviluppo di moduli.  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Applicazione di attributi](applying-attributes.md)|Descrive come applicare un attributo a un elemento di codice.|  
|[Scrittura di attributi personalizzati](writing-custom-attributes.md)|Descrive come progettare le classi di attributi personalizzati.|  
|[Recupero di informazioni memorizzate negli attributi](retrieving-information-stored-in-attributes.md)|Descrive come recuperare attributi personalizzati per codice che viene caricato nel contesto di esecuzione.|  
|[Metadati e componenti auto-descrittivi](../metadata-and-self-describing-components.md)|Fornisce una panoramica dei metadati e descrive come vengono implementati in un file eseguibile (PE) di .NET Framework.|  
|[Procedura: Caricare assembly nel contesto Reflection-Only](../../framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)|Illustra come recuperare informazioni sugli attributi personalizzati nel contesto reflection-only.|  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Attribute?displayProperty=nameWithType>
