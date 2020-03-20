---
title: Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: cbde2af9c8a03e6c41f571120027030713f1b8d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73104121"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
Lo [strumento Utilità di esportazione della libreria dei tipi](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carica una libreria a collegamento dinamico denominata TlbRef. Questa DLL contiene due funzioni di supporto e un'interfaccia usata dall'utilità di esportazione durante il processo di conversione da assembly a libreria dei tipi.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Funzione GetTypeLibInfo](gettypelibinfo-function.md)  
 Fornisce informazioni sulla localizzazione e il sistema operativo per una libreria dei tipi.  
  
 [Funzione LoadTypeLibWithResolver](loadtypelibwithresolver-function.md)  
 Carica una libreria dei tipi usando un'implementazione dell'[interfaccia ITypeLibResolver](itypelibresolver-interface.md) per risolvere le librerie dei tipi a cui viene fatto riferimento.  
  
 [Interfaccia ITypeLibResolver](itypelibresolver-interface.md)  
 Fornisce il [metodo ResolveTypeLib](resolvetypelib-method.md), che restituisce il percorso completo di una libreria dei tipi.
