---
title: Valore checksum non valido. Cifre esadecimali non presenti o in numero dispari
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: e682c2c23dd6fe80aee87d2a86b3df2dae66b802
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45677500"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a>Valore checksum non valido. Cifre esadecimali non presenti o in numero dispari
Un valore di checksum include cifre esadecimali non valide o un numero di cifre dispari.  
  
 Quando ASP.NET genera un file di origine Visual Basic, con estensione vb, calcola un checksum e lo colloca in un file di origine nascosto identificato da `#externalchecksum`. Anche un utente può generare un file con estensione vb per lo stesso scopo, ma questo processo è più adatto per essere usato internamente.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42033  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Se il file di origine Visual Basic viene generato da ASP.NET, riavviare la compilazione del progetto.  
  
2.  Se l'avviso persiste dopo il riavvio, reinstallare ASP.NET e riprovare a eseguire la compilazione.  
  
3.  Se l'avviso persiste ancora o non si usa ASP.NET, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ASP.NET](/aspnet/overview)  
- [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
