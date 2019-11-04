---
title: 'Mitigazione: Rendering di finestre WPF'
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: 42d6abf1ba6ed7c17a5a5604e98b5ee46d0c3ac2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457775"
---
# <a name="mitigation-wpf-window-rendering"></a>Mitigazione: Rendering di finestre WPF

In .NET Framework 4.6 in esecuzione su Windows 8 e versioni successive viene eseguito il rendering dell'intera finestra senza ritaglio quando la finestra si estende al di fuori di un singolo schermo in uno scenario d'uso di più monitor.

## <a name="impact"></a>Impatto

In generale, il rendering di un'intera finestra su più monitor senza ritaglio è il comportamento previsto. Tuttavia, in Windows 7 e versioni precedenti le finestre WPF vengono ritagliate quando si estendono oltre un singolo schermo perché il rendering di una parte della finestra sul secondo monitor ha un impatto significativo sulle prestazioni.

L'impatto esatto del rendering di finestre WPF su più monitor in Windows 8 e versioni successive non è precisamente quantificabile poiché dipende da numerosi fattori. In alcuni casi, potrebbe produrre un impatto indesiderato sulle prestazioni, in particolare per gli utenti che eseguono applicazioni a elevato utilizzo di grafica e hanno finestre che si estendono su più monitor. In altri casi, si potrebbe semplicemente volere un comportamento coerente tra le versioni di .NET Framework.

## <a name="mitigation"></a>Attenuazione

È possibile disabilitare questa modifica e ripristinare il comportamento precedente di ritaglio di una finestra WPF quando si estende oltre un singolo schermo. Questo risultato può essere raggiunto in due modi:

- Aggiungendo l'elemento `<EnableMultiMonitorDisplayClipping>` nella sezione `<appSettings>` del file di configurazione dell'applicazione, è possibile disabilitare o abilitare questo comportamento nelle app che eseguono Windows 8 o versione successiva. Ad esempio, la sezione di configurazione seguente disabilita il rendering senza ritaglio:

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  L'impostazione di configurazione `<EnableMultiMonitorDisplayClipping>` può avere uno dei due valori seguenti:

  - `true` per consentire il ritaglio delle finestre in base ai confini del monitor durante il rendering.

  - `false` per disabilitare il ritaglio delle finestre in base ai confini del monitor durante il rendering.

- Impostando la proprietà <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> su `true` all'avvio dell'app.

## <a name="see-also"></a>Vedere anche

- [Compatibilità delle applicazioni](application-compatibility.md)
