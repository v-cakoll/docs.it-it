---
title: Esposizione di componenti COM a .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20ec022f378feba3368ea79fdd5c6ee7ecccf1b9
ms.sourcegitcommit: 56ac30a336668124cb7d95d8ace16bd985875147
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2019
ms.locfileid: "65469647"
---
# <a name="exposing-com-components-to-the-net-framework"></a>Esposizione di componenti COM a .NET Framework
Questa sezione riepiloga il processo necessario per esporre un componente COM esistente al codice gestito. Per informazioni dettagliate sulla scrittura di server COM strettamente integrati con .NET Framework, vedere [Considerazioni di progettazione per l'interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).
  
 I componenti COM esistenti sono risorse preziose nel codice gestito come applicazioni aziendali di livello intermedio o come funzionalità isolate. Un componente ideale ha un assembly di interoperabilità primario ed è strettamente conforme agli standard di programmazione imposti da COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Per esporre i componenti COM a .NET Framework  
  
1. [Importare una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md).  
  
     Common Language Runtime richiede metadati per tutti i tipi, inclusi i tipi COM. Un assembly contenente tipi COM importati come metadati può essere ottenuto in diversi modi.  
  
2. [Usare i tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).  
  
     È possibile esaminare i tipi COM, attivare istanze e richiamare i metodi sull'oggetto COM esattamente come per gli altri tipi gestiti.  
  
3. [Compilare un progetto di interoperabilità](compiling-an-interop-project.md).  
  
     [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] specifica i compilatori per diversi linguaggi conformi alle specifiche CLS, inclusi Visual Basic, C# e C++.  
  
4. [Distribuire un'applicazione di interoperabilità](deploying-an-interop-application.md).  
  
     Per una distribuzione ottimale delle applicazioni di interoperabilità, distribuirle come assembly firmati [con nome sicuro](../app-domains/strong-named-assemblies.md) nella Global Assembly Cache.  
  
## <a name="see-also"></a>Vedere anche

- [Interoperabilità con codice non gestito](index.md)
- [Considerazioni di progettazione per l'interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))
- [Esempio di interoperabilità COM: client .NET e server COM](com-interop-sample-net-client-and-com-server.md)
- [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../standard/language-independence-and-language-independent-components.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md)
