---
ms.openlocfilehash: a5c6dda0c1d68468cd95f67716709dd059948c80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621340"
---
### <a name="product-versioning-changes-in-the-net-framework-46-and-later-versions"></a>Modifiche apportate al controllo delle versioni del prodotto in .NET Framework 4.6 e versioni successive

#### <a name="details"></a>Dettagli

Il controllo delle versioni del prodotto è cambiato rispetto alle versioni precedenti di .NET Framework, in particolare rispetto a .NET Framework 4, 4.5, 4.5.1 e 4.5.2. Di seguito sono illustrate in modo dettagliato le modifiche:<ul><li>Il valore della voce <code>Version</code> nella chiave <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code> è stato modificato in <code>4.6.xxxxx</code> per .NET Framework 4.6 e versioni intermedie e in <code>4.7.xxxxx</code> per .NET Framework 4.7 e 4.7.1. In .NET Framework 4.5, 4.5.1 e 4.5.2, il formato era <code>4.5.xxxxx</code>.</li><li>Il controllo delle versioni di file e prodotti per i file di .NET Framework è stato modificato dal precedente schema di controllo delle versioni 4.0.30319.x in 4.6.X.0 per .NET Framework 4.6 e versioni intermedie e in 4.7.X.0 per .NET Framework 4.7 e 4.7.1. È possibile visualizzare questi nuovi valori scegliendo Proprietà dopo aver fatto clic con il pulsante destro del mouse su un file.</li><li>Gli attributi <xref:System.Reflection.AssemblyFileVersionAttribute> e <xref:System.Reflection.AssemblyInformationalVersionAttribute> per gli assembly gestiti presentano valori di versione nel formato 4.6.X.0 per .NET Framework 4.6 e versioni intermedie e 4.7.X.0 per .NET Framework 4.7 e 4.7.1.</li><li>In .NET Framework 4.6, 4.6.1, 4.6.2, 4.7 e 4.7.1 la proprietà <xref:System.Environment.Version?displayProperty=nameWithType> restituisce la stringa di versione fissa <code>4.0.30319.42000</code>. In .NET Framework 4, 4.5, 4.5.1 e 4.5.2 restituisce le stringhe di versione nel formato <code>4.0.30319.xxxxx</code> (ad esempio, &quot;4.0.30319.18010&quot;). Si noti che è sconsigliabile che il codice di applicazione acquisisca nuove dipendenze dalla proprietà Environment.Version.</li></ul>Per altre informazioni, vedere [Procedura: Determinare le versioni di .NET Framework installate](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

#### <a name="suggestion"></a>Suggerimento

In generale, le applicazioni dovrebbero dipendere dalle tecniche consigliate per il rilevamento di elementi come la versione di runtime di .NET Framework e la directory di installazione:<ul><li>Per rilevare la versione di runtime di .NET Framework, vedere [Procedura: Determinare le versioni di .NET Framework installate](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</li><li>Per determinare il percorso di installazione di .NET Framework, usare il valore della voce <code>InstallPath</code> nella chiave <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code>.</li></ul> <blockquote> [!IMPORTANT] Il nome della sottochiave è <code>NET Framework Setup</code>, non <code>.NET Framework Setup</code>.</blockquote> <ul><li>Per determinare il percorso di directory a Common Language Runtime di .NET Framework, chiamare il metodo <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory?displayProperty=nameWithType>.</li><li>Per ottenere la versione CLR, chiamare il metodo <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion?displayProperty=nameWithType>. Per .NET Framework 4 e versioni intermedie (.NET Framework 4.5, 4.5.1, 4.5.2 e .NET Framework 4.6, 4.6.1, 4.6.2, 4.7 e 4.7.1), restituisce la stringa v4.0.30319.</li></ul>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6|
|Type|Runtime|
