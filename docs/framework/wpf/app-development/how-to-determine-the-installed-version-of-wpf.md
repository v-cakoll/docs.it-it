---
title: Determinare la versione installata di WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: 8fc5c380779891b44b7c4f7f8aeb5ed119d8b768
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735690"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Procedura: determinare la versione installata di WPF
Il numero di versione per la versione installata corrente di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] si trova nel **Registro di sistema**.  
  
 Per trovare il numero di versione:  
  
1. Fare clic sul pulsante **Start** , quindi scegliere **Esegui**.  
  
2. In **Apri**Digitare **Regedit. exe**.  
  
3. Aprire la chiave seguente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 Il numero di versione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene archiviato nel valore della **versione** .
