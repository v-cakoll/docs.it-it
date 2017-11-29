---
title: Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5d0a0b08be725a50442a3db9f9942bceea7cf8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
Il [strumento Type Library Exporter](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carica una libreria a collegamento dinamico denominata TlbRef. Questa DLL contiene due funzioni di supporto e un'interfaccia che utilizza l'utilità di esportazione durante il processo di conversione da assembly a libreria.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [GetTypeLibInfo (funzione)](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Fornisce informazioni di localizzazione e del sistema operativo per una libreria dei tipi.  
  
 [LoadTypeLibWithResolver (funzione)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Carica una libreria dei tipi tramite un'implementazione del [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere gli eventuali librerie dei tipi di riferimento.  
  
 [Interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Fornisce il [metodo ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), che restituisce il percorso completo di una libreria dei tipi.
