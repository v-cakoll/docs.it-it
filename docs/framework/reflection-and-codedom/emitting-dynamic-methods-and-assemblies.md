---
title: Creazione di assembly e metodi dinamici
ms.custom: 
ms.date: 08/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 91b0cc4614834f2ad8f7b54d9364d484ca9a6990
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="emitting-dynamic-methods-and-assemblies"></a>Creazione di assembly e metodi dinamici
Questa sezione descrive un insieme di tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit> che consentono la creazione di metadati e codice MSIL (Microsoft Intermediate Language) da parte di compilatori o strumenti in fase di esecuzione ed eventualmente la generazione su disco di un file eseguibile portabile (PE, Portable Executable). Questo spazio dei nomi viene usato principalmente da moduli di gestione di script e compilatori. In questa sezione si farà riferimento alle funzionalità fornite dallo spazio dei nomi <xref:System.Reflection.Emit> con l'espressione reflection emit (creazione tramite la reflection).   
  
 La reflection emit offre le funzionalità seguenti:   
  
-   Definizione di metodi globali di tipo lightweight in fase di esecuzione mediante la classe <xref:System.Reflection.Emit.DynamicMethod> ed esecuzione di tali metodi mediante delegati.  
  
-   Definizione di assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.  
  
-   Definizione di assembly in fase di esecuzione, quindi esecuzione e scaricamento per consentire al processo di Garbage Collection di recuperare le risorse.  
  
-   Definizione di moduli in nuovi assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.  
  
-   Definizione di tipi in moduli in fase di esecuzione, creazione di istanze di tali tipi e chiamate ai relativi metodi.  
  
-   Definizione di informazioni relative ai simboli per i moduli definiti, che possono essere usate da strumenti quali debugger e analizzatori di codice.  
  
 Oltre ai tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit>, sono disponibili interfacce di metadati non gestite, descritte nella documentazione di riferimento per le [interfacce di metadati](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md). La reflection emit gestita garantisce un controllo degli errori semantici più completo e un livello di astrazione dei metadati più alto rispetto alle interfacce di metadati non gestite.  
  
 Un'altra risorsa per l'uso di metadati e codice MSIL è la documentazione CLI (Common Language Infrastructure), in particolare la seconda e la terza parte, relative rispettivamente alla semantica e alla definizione dei metadati e all'insieme di istruzioni. La documentazione è disponibile online su [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) e sul [sito Web di ECMA](http://go.microsoft.com/fwlink/?LinkId=116487).  
  
## <a name="in-this-section"></a>Contenuto della sezione
  
[Problemi di sicurezza nella reflection emit](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
Descrive i problemi di sicurezza relativi alla creazione di assembly dinamici mediante la reflection emit.  

[Procedura: definire ed eseguire metodi dinamici](how-to-define-and-execute-dynamic-methods.md)   
Viene illustrato come eseguire un metodo dinamico semplice e un metodo dinamico associato a un'istanza di una classe.

[Procedura: definire un tipo generico tramite reflection emit](how-to-define-a-generic-type-with-reflection-emit.md)   
Viene illustrato come creare un tipo generico semplice con due parametri di tipo, come applicare classi, interfacce e i vincoli speciali per i parametri di tipo e come creare memers che utilizzano i parametri di tipo della classe come tipi di parametri e tipi restituiti.

[Procedura: definire un metodo generico tramite reflection emit](how-to-define-a-generic-method-with-reflection-emit.md)   
Viene illustrato come creare, creare e richiamare un metodo generico semplice.

[Assembly ritirabili per la generazione di tipo dinamico](collectible-assemblies.md)   
Introduce assembly ritirabile, ovvero gli assembly dinamici che possono essere scaricati senza scaricare il dominio applicazione in cui sono stati creati.
  
## <a name="reference"></a>Riferimento  
 <xref:System.Reflection.Emit.OpCodes>  
 Cataloga i codici di istruzioni MSIL che è possibile usare per compilare i corpi dei metodi.  
  
 <xref:System.Reflection.Emit>  
 Contiene le classi gestite usate per creare metodi, assembly e tipi dinamici.  
  
 <xref:System.Type>  
 Illustra la classe <xref:System.Type>, che rappresenta i tipi nella reflection gestita e nella reflection emit, e descrive i concetti fondamentali relativi all'uso di queste tecnologie.  
  
 <xref:System.Reflection>  
 Contiene le classi gestite usate per esaminare i metadati e il codice gestito.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Illustra come esaminare i metadati e il codice gestito.  
  
 [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Fornisce una panoramica degli assembly in implementazioni di .NET.
