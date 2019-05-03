---
title: 'Procedura: Determinare la versione installata di WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052456"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Procedura: Determinare la versione installata di WPF
Il numero di versione per la versione attualmente installata di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] si trova nel **registro**.  
  
 Per trovare il numero di versione:  
  
1. Fare clic sul pulsante **Start** , quindi scegliere **Esegui**.  
  
2. Nelle **aperto**, digitare **regedit.exe**.  
  
3. Aprire la chiave seguente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] numero di versione viene archiviato nel **versione** valore.
