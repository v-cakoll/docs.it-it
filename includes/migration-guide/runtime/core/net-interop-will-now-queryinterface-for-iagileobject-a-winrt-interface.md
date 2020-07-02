---
ms.openlocfilehash: 150b94b55fa8f2a29f1da7cf7ac7bf6dd06b9666
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621981"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>L'interoperabilità di .NET ora usa QueryInterface per IAgileObject, un'interfaccia WinRT

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.8, quando si usa un evento WinRT con un delegato di .NET, Windows usa QI per IAgileObject.  Nelle versioni precedenti di .NET Framework il runtime non riusciva a usare QI e non era possibile sottoscrivere l'evento.<ul><li>[ x ] Anomalo</li></ul>

#### <a name="suggestion"></a>Suggerimento

Se l'abilitazione di QI per IAgileObject interrompe l'esecuzione, è possibile disabilitare questo codice impostando la configurazione seguente. <h4>Metodo 1: variabile di ambiente</h4> Impostare la variabile di ambiente seguente: COMPLUS_DisableCCWSupportIAgileObject=1Questo metodo influisce su tutti gli ambienti che ereditano la variabile. Potrebbe trattarsi di una singola sessione della console o potrebbe influire sull'intero computer se si imposta la variabile di ambiente a livello globale. Il nome della variabile di ambiente non distingue tra maiuscole e minuscole. <h4>Metodo 2: Registro di sistema</h4> Usando l'editor del registro di sistema (regedit.exe), trovare una delle sottochiavi seguenti: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER \SOFTWARE\Microsoft.NETFrameworkThen aggiungere quanto segue: nome valore: DisableCCWSupportIAgileObject tipo: DWORD (32-bit) valore (chiamato anche REG_WORD) valore: 1You può usare lo strumento Windows REG.EXE per aggiungere questo valore da un ambiente di riga di comando o di scripting. Ad esempio:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>In questo caso viene usato <code>HKLM</code> invece di <code>HKEY_LOCAL_MACHINE</code>. Usare <code>reg add /?</code> per visualizzare la guida su questa sintassi. Il nome del valore del registro di sistema non distingue tra maiuscole e minuscole.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.8|
|Type|Runtime|
