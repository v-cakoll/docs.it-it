---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620401"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>I controlli di hosting di browser gestiti da .NET Framework 1.1 e 2.0 sono bloccati

#### <a name="details"></a>Dettagli

L'hosting di questi controlli è bloccato in Internet Explorer.

#### <a name="suggestion"></a>Suggerimento

Internet Explorer non riuscirà ad avviare un'applicazione che usa controlli di hosting di browser gestiti. È possibile ripristinare il comportamento precedente impostando il valore EnableIEHosting della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> su <code>1</code> per i sistemi x86 e i processi a 32 bit nei sistemi x64 e impostando il valore <code>EnableIEHosting</code> della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> su <code>1</code> per i processi a 64 bit nei sistemi x64.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime|
