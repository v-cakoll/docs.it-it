---
ms.openlocfilehash: 5b3f9bcb56d3e34568afd8b97fb9ebe09a677f4c
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802607"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>L'interoperabilità di .NET ora usa QueryInterface per IAgileObject, un'interfaccia WinRT

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.8, quando si usa un evento WinRT con un delegato di .NET, Windows usa QI per IAgileObject.  Nelle versioni precedenti di .NET Framework il runtime non riusciva a usare QI e non era possibile sottoscrivere l'evento.<ul><li>[ x ] Anomalo</li></ul>|
|Suggerimento|Se l'abilitazione di QI per IAgileObject interrompe l'esecuzione, è possibile disabilitare questo codice impostando la configurazione seguente. <h4>Metodo 1: Variabile di ambiente</h4> Impostare la variabile di ambiente seguente: COMPLUS_DisableCCWSupportIAgileObject=1Questo metodo influisce su tutti gli ambienti che ereditano la variabile. Può trattarsi di una singola sessione di console o può riguardare l'intero computer se la variabile di ambiente viene impostata a livello globale.Il nome della variabile di ambiente non distingue tra maiuscole/minuscole. <h4>Metodo 2: Registro di sistema</h4> Usando l'editor del Registro di sistema (regedit.exe), trovare una delle sottochiavi seguenti:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkIn seguito aggiungere quanto segue:Nome valore: DisableCCWSupportIAgileObject Tipo: valore DWORD (32-bit) (detto anche REG_WORD) Valore: 1È possono usare lo strumento Windows REG.EXE per aggiungere questo valore da una riga di comando o da un ambiente di scripting. Ad esempio:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>In questo caso viene usato <code>HKLM</code> invece di <code>HKEY_LOCAL_MACHINE</code>. Usare <code>reg add /?</code> per visualizzare la guida per questa sintassi.Il nome del valore del Registro di sistema non distingue tra maiuscole/minuscole.|
|Ambito|Microsoft Edge|
|Versione|4.8|
|Tipo|Runtime|

