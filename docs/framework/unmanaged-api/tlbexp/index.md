---
title: Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
Il [strumento Type Library Exporter](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carica una libreria a collegamento dinamico denominata TlbRef. Questa DLL contiene due funzioni di supporto e un'interfaccia che utilizza l'utilità di esportazione durante il processo di conversione da assembly a libreria.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione GetTypeLibInfo](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Fornisce informazioni di localizzazione e del sistema operativo per una libreria dei tipi.  
  
 [Funzione LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Carica una libreria dei tipi tramite un'implementazione del [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere gli eventuali librerie dei tipi di riferimento.  
  
 [Interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Fornisce il [metodo ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), che restituisce il percorso completo di una libreria dei tipi.
