---
title: Creazione di assembly e metodi dinamici
description: Creare assembly e metodi dinamici utilizzando lo spazio dei nomi System. Reflection. Emit, che consente a un compilatore o a uno strumento di creare metadati e codice MSIL in fase di esecuzione.
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: 76d2a83943d9df06cc66cf86c6869f18fac2a12c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475047"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a>Creazione di assembly e metodi dinamici

Questa sezione descrive un insieme di tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit> che consentono la creazione di metadati e codice MSIL (Microsoft Intermediate Language) da parte di compilatori o strumenti in fase di esecuzione ed eventualmente la generazione su disco di un file eseguibile portabile (PE, Portable Executable). Questo spazio dei nomi viene usato principalmente da moduli di gestione di script e compilatori. In questa sezione si farà riferimento alle funzionalità fornite dallo spazio dei nomi <xref:System.Reflection.Emit> con l'espressione reflection emit (creazione tramite la reflection).   
  
La reflection emit offre le funzionalità seguenti:   
  
- Definizione di metodi globali di tipo lightweight in fase di esecuzione mediante la classe <xref:System.Reflection.Emit.DynamicMethod> ed esecuzione di tali metodi mediante delegati.  
  
- Definizione di assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.  
  
- Definizione di assembly in fase di esecuzione, quindi esecuzione e scaricamento per consentire al processo di Garbage Collection di recuperare le risorse.  
  
- Definizione di moduli in nuovi assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.  
  
- Definizione di tipi in moduli in fase di esecuzione, creazione di istanze di tali tipi e chiamate ai relativi metodi.  
  
- Definizione di informazioni relative ai simboli per i moduli definiti, che possono essere usate da strumenti quali debugger e analizzatori di codice.  
  
Oltre ai tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit>, sono disponibili interfacce di metadati non gestite, descritte nella documentazione di riferimento per le [interfacce di metadati](../unmanaged-api/metadata/metadata-interfaces.md). La reflection emit gestita garantisce un controllo degli errori semantici più completo e un livello di astrazione dei metadati più alto rispetto alle interfacce di metadati non gestite.  
  
Un'altra risorsa per l'uso di metadati e codice MSIL è la documentazione CLI (Common Language Infrastructure), in particolare la seconda e la terza parte, relative rispettivamente alla semantica e alla definizione dei metadati e all'insieme di istruzioni. La documentazione è disponibile online nel [sito Web ECMA](https://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="in-this-section"></a>Contenuto della sezione
  
[Problemi di sicurezza nella Reflection Emit](security-issues-in-reflection-emit.md)  
Descrive i problemi di sicurezza relativi alla creazione di assembly dinamici mediante la reflection emit.  

[Procedura: definire ed eseguire metodi dinamici](how-to-define-and-execute-dynamic-methods.md) Viene illustrato come eseguire un metodo dinamico semplice e un metodo dinamico associato a un'istanza di una classe.

[Procedura: definire un tipo generico tramite reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Viene illustrato come creare un tipo generico semplice con due parametri di tipo, come applicare vincoli di classe, interfaccia e speciali ai parametri di tipo e come creare membri che usano i parametri di tipo della classe come tipi di parametro e tipi restituiti.

[Procedura: definire un metodo generico tramite reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Viene illustrato come creare, emettere e richiamare un metodo generico semplice.

Assembly ritirabili [per la generazione di tipi dinamici](collectible-assemblies.md) Introduce assembly ritirabili, che sono assembly dinamici che possono essere scaricati senza scaricare il dominio dell'applicazione in cui sono stati creati.
  
## <a name="reference"></a>Informazioni di riferimento  

<xref:System.Reflection.Emit.OpCodes>  
Cataloga i codici di istruzioni MSIL che è possibile usare per compilare i corpi dei metodi.  
  
<xref:System.Reflection.Emit>  
Contiene le classi gestite usate per creare metodi, assembly e tipi dinamici.  
  
<xref:System.Type>  
Illustra la classe <xref:System.Type>, che rappresenta i tipi nella reflection gestita e nella reflection emit, e descrive i concetti fondamentali relativi all'uso di queste tecnologie.  
  
<xref:System.Reflection>  
Contiene le classi gestite usate per esaminare i metadati e il codice gestito.  
  
## <a name="related-sections"></a>Sezioni correlate  

[Reflection](reflection.md)  
Illustra come esaminare i metadati e il codice gestito.  
  
[Assembly in .NET](../../standard/assembly/index.md)  
Fornisce una panoramica degli assembly nelle implementazioni .NET.
