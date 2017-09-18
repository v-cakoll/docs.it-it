---
title: Esposizione di componenti COM a .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c0fcf7bec289d64b1faceef00b01278fa45caab0
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="exposing-com-components-to-the-net-framework"></a>Esposizione di componenti COM a .NET Framework
Questa sezione riepiloga il processo necessario per esporre un componente COM esistente al codice gestito. Per informazioni dettagliate sulla scrittura di server COM strettamente integrati con .NET Framework, vedere [Considerazioni di progettazione per l'interoperabilità](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 I componenti COM esistenti sono risorse preziose nel codice gestito come applicazioni aziendali di livello intermedio o come funzionalità isolate. Un componente ideale ha un assembly di interoperabilità primario ed è strettamente conforme agli standard di programmazione imposti da COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Per esporre i componenti COM a .NET Framework  
  
1.  [Importare una libreria dei tipi come assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Common Language Runtime richiede metadati per tutti i tipi, inclusi i tipi COM. Un assembly contenente tipi COM importati come metadati può essere ottenuto in diversi modi.  
  
2.  [Creare tipi COM nel codice gestito](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     È possibile esaminare i tipi COM, attivare istanze e richiamare i metodi sull'oggetto COM esattamente come per gli altri tipi gestiti.  
  
3.  [Compilare un progetto di interoperabilità](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] fornisce i compilatori per diversi linguaggi conformi alle specifiche CLS, inclusi [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# e C++.  
  
4.  [Distribuire un'applicazione di interoperabilità](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     Per una distribuzione ottimale delle applicazioni di interoperabilità, distribuirle come assembly firmati [con nome sicuro](../../../docs/framework/app-domains/strong-named-assemblies.md) nella Global Assembly Cache.  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md)   
 [Considerazioni di progettazione per l'interoperabilità](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)   
 [Esempio di interoperabilità COM: client .NET e server COM](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)   
 [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Gacutil.exe (strumento Global Assembly Cache)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)

