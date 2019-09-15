---
ms.openlocfilehash: 0036fc2b03dde64d24d883e55b9f00c931f0c218
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70997637"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>L'interoperabilità di .NET ora usa QueryInterface per IAgileObject, un'interfaccia WinRT

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.8, quando si usa un evento WinRT con un delegato di .NET, Windows usa QI per IAgileObject.  Nelle versioni precedenti di .NET Framework il runtime non riusciva a usare QI e non era possibile sottoscrivere l'evento.<ul><li>[ x ] Anomalo</li></ul>|
|Suggerimento|Se l'abilitazione di QI per IAgileObject interrompe l'esecuzione, è possibile disabilitare questo codice impostando la configurazione seguente. <h4>Metodo 1: Variabile di ambiente</h4> Impostare la variabile di ambiente seguente: COMPLUS_DisableCCWSupportIAgileObject=1Questo metodo influisce su tutti gli ambienti che ereditano la variabile. Potrebbe trattarsi di una singola sessione della console o potrebbe influire sull'intero computer se si imposta la variabile di ambiente a livello globale. Il nome della variabile di ambiente non distingue tra maiuscole e minuscole. <h4>Metodo 2: Registro</h4> Usando l'editor del Registro di sistema (regedit.exe), trovare una delle sottochiavi seguenti:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkIn seguito aggiungere quanto segue:Nome valore: DisableCCWSupportIAgileObject Tipo: valore DWORD (32-bit) (detto anche REG_WORD) Valore: 1È possono usare lo strumento Windows REG.EXE per aggiungere questo valore da una riga di comando o da un ambiente di scripting. Ad esempio:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>In questo caso viene usato <code>HKLM</code> invece di <code>HKEY_LOCAL_MACHINE</code>. Usare <code>reg add /?</code> per visualizzare la guida su questa sintassi. Il nome del valore del registro di sistema non distingue tra maiuscole e minuscole.|
|Ambito|Microsoft Edge|
|Versione|4.8|
|Type|Runtime|
