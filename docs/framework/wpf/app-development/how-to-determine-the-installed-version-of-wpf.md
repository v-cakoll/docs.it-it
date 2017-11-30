---
title: 'Procedura: determinare la versione installata di WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60f2dd65702a5dfcff4cbafa97e5a48080b8e5be
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Procedura: determinare la versione installata di WPF
Il numero di versione per la versione attualmente installata di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] si trova nella **Registro di sistema**.  
  
 Per trovare il numero di versione:  
  
1.  Fare clic sul pulsante **Start** , quindi scegliere **Esegui**.  
  
2.  In **aprire**, tipo **regedit.exe**.  
  
3.  Aprire la chiave seguente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il numero di versione viene archiviato nel **versione** valore.
