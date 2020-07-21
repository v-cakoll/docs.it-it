---
title: 'Mitigazione: Controllo delle versioni del prodotto'
description: In questo articolo viene illustrato come .NET Framework 4,6 e versioni successive del prodotto sono state modificate rispetto alle versioni precedenti.
ms.date: 03/30/2017
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
ms.openlocfilehash: 442c06446e763758d3a150ee9ff884a616541c07
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475398"
---
# <a name="mitigation-product-versioning"></a>Mitigazione: Controllo delle versioni del prodotto

In .NET Framework 4.6 e versioni successive il controllo delle versioni del prodotto è cambiato rispetto alle versioni precedenti di .NET Framework (.NET Framework 4, 4.5, 4.5.1 e 4.5.2).

## <a name="product-versioning-changes"></a>Modifiche apportate al controllo delle versioni del prodotto

Di seguito sono illustrate in modo dettagliato le modifiche:

- Il valore della voce `Version` nella chiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` è stato modificato in `4.6.`*xxxxx* per .NET Framework 4.6 e versioni intermedie e in `4.7.`*xxxxx* per .NET Framework 4.7. In .NET Framework 4.5, 4.5.1 e 4.5.2, il formato era `4.5.`*xxxxx*.

- Il controllo delle versioni di file e prodotti per i file di .NET Framework è stato modificato dal precedente schema di controllo delle versioni `4.0.30319.x` in `4.6.X.0` per .NET Framework 4.6 e versioni intermedie e in `4.7.X.0` per .NET Framework 4.7 e versioni intermedie. È possibile visualizzare questi nuovi valori quando si visualizzano le **Proprietà** del file dopo aver fatto clic con il pulsante destro del mouse su un file.

- Gli attributi <xref:System.Reflection.AssemblyFileVersionAttribute> e <xref:System.Reflection.AssemblyInformationalVersionAttribute> per gli assembly gestiti hanno valori <xref:System.Version> nel formato `4.6.X.0` per .NET Framework 4.6 e versioni intermedie e `4.7.X.0` per .NET Framework 4.7.

- A partire da .NET Framework 4.6, la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> restituisce la stringa di versione fissa `4.0.30319.42000`. In .NET Framework 4, 4.5, 4.5.1 e 4.5.2, restituisce le stringhe di versione nel formato `4.0.30319.xxxxx`, dove `xxxxx` è inferiore a 42000 (ad esempio, "4.0.30319.18010"). Si noti che è sconsigliabile che il codice di applicazione acquisisca nuove dipendenze dalla proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType>.

### <a name="handling-the-product-versioning-changes"></a>Gestione delle modifiche apportate al controllo delle versioni del prodotto

In generale, le applicazioni dovrebbero dipendere dalle tecniche consigliate per il rilevamento di elementi come la versione di runtime di .NET Framework e la directory di installazione:

- Per rilevare la versione di runtime di .NET Framework, vedere [Procedura: Determinare le versioni di .NET Framework installate](how-to-determine-which-versions-are-installed.md).

- Per determinare il percorso di installazione di .NET Framework, usare il valore della voce `InstallPath` nella chiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`.

  > [!IMPORTANT]
  > Il nome della sottochiave è `NET Framework Setup`, non `.NET Framework Setup`.

- Per determinare il percorso di directory a Common Language Runtime di .NET Framework, chiamare il metodo <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType>.

- Per ottenere la versione CLR, chiamare il metodo <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType>.   Per .NET Framework 4 e versioni intermedie (.NET Framework 4.5, 4.5.1, 4.5.2 e .NET Framework 4.6, 4.6.1, 4.6.2 e 4.7), restituisce la stringa `v4.0.30319`.

## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
