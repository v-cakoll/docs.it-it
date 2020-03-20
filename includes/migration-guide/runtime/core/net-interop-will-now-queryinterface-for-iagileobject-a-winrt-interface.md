---
ms.openlocfilehash: 0036fc2b03dde64d24d883e55b9f00c931f0c218
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997637"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>L'interoperabilità di .NET ora usa QueryInterface per IAgileObject, un'interfaccia WinRT

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.8, quando si usa un evento WinRT con un delegato di .NET, Windows usa QI per IAgileObject.  Nelle versioni precedenti di .NET Framework il runtime non riusciva a usare QI e non era possibile sottoscrivere l'evento.<ul><li>[ x ] Anomalo</li></ul>|
|Suggerimento|Se l'abilitazione di QI per IAgileObject interrompe l'esecuzione, è possibile disabilitare questo codice impostando la configurazione seguente. <h4>Metodo 1: Variabile di ambiente</h4> Impostare la variabile di ambiente seguente: COMPLUS_DisableCCWSupportIAgileObject=1Questo metodo influisce su tutti gli ambienti che ereditano la variabile. Potrebbe trattarsi di una singola sessione della console o dell'intero computer se si imposta la variabile di ambiente a livello globale. Per il nome della variabile di ambiente non viene fatta distinzione tra maiuscole e minuscole. <h4>Metodo 2: Registro di sistema</h4> Utilizzando l'editor del Registro di sistema (regedit.exe), trovare una delle seguenti sottochiavi:HKEY_LOCAL_MACHINE SOFTWARE Microsoft.NETFramework HKEY_CURRENT_USER SOFTWARE Microsoft.NETFrameworkPoi aggiungere il seguente:Nome valore: DisableCCWSupportIAgileObject Tipo: Valore DWORD (32 bit) (chiamato anche REG_WORD) Valore: 1È possibile utilizzare Windows REG. EXE per aggiungere questo valore da una riga di comando o da un ambiente di scripting. Ad esempio:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>In questo caso viene usato <code>HKLM</code> invece di <code>HKEY_LOCAL_MACHINE</code>. Utilizzare <code>reg add /?</code> per visualizzare la Guida su questa sintassi. Il nome del valore del Registro di sistema non fa distinzione tra maiuscole e minuscole.|
|Scope|Microsoft Edge|
|Versione|4.8|
|Type|Runtime|
