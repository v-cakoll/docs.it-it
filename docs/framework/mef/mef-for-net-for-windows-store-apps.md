---
title: MEF per .NET per app Windows Store
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2b62e6fea6da46e6307b35dd1c3372420dced80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648504"
---
# <a name="mef-for-net-for-windows-store-apps"></a>MEF per .NET per app Windows Store
<xref:System.Composition?displayProperty=nameWithType> e i relativi spazi dei nomi figlio contengono i tipi per sviluppare app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] estendibili mediante Managed Extensibility Framework (MEF). Questi spazi dei nomi fanno parte del subset [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] per il sistema operativo [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
 Questi spazi dei nomi non fanno parte della libreria di classi principale distribuita con .NET Framework. Per installare questi spazi dei nomi, aprire il progetto in Visual Studio, scegliere **Gestisci pacchetti NuGet** dal menu **Progetto** e cercare online il pacchetto Microsoft.Composition.  
  
- <xref:System.Composition?displayProperty=nameWithType> fornisce classi che costituiscono il framework MEF di base per le app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
- <xref:System.Composition.Convention?displayProperty=nameWithType> fornisce i tipi che supportano l'uso di MEF con un modello di configurazione basato sulle convenzioni.  
  
- <xref:System.Composition.Hosting?displayProperty=nameWithType> fornisce tipi MEF utili agli sviluppatori di applicazioni host.  
  
- <xref:System.Composition.Hosting.Core?displayProperty=nameWithType> fornire i tipi MEF usati internamente dal motore di composizione.  
  
 Per altre informazioni su [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] e un elenco degli spazi dei nomi e dei tipi contenuti, vedere [Panoramica di .NET per le app di Windows Store](https://go.microsoft.com/fwlink/p/?LinkID=238312) nel Centro sviluppatori Windows.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di .NET per le app di Windows Store](https://go.microsoft.com/fwlink/p/?LinkID=238312)
- [.NET per app di Windows Store – API supportate](https://go.microsoft.com/fwlink/p/?LinkID=247912)
- [Managed Extensibility Framework (MEF)](../../../docs/framework/mef/index.md)
