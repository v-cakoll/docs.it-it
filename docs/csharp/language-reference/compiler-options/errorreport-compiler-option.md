---
title: -errorreport (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 52b58aac5e82d4228dfda9c4d77c1d1c5de3e0cd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253888"
---
# <a name="-errorreport-c-compiler-options"></a>-errorreport (opzioni del compilatore C#)
Questa opzione rappresenta un modo pratico per segnalare a Microsoft un errore del compilatore interno C#.

> [!NOTE]
> In Windows Vista e Windows Server 2008 le impostazioni di segnalazione errori apportate per Visual Studio non eseguono l'override delle impostazioni apportate tramite Segnalazioni errori Windows. Le impostazioni di Segnalazione errori Windows hanno sempre la precedenza sulle impostazioni della funzione di segnalazione errori di Visual Studio.

## <a name="syntax"></a>Sintassi

```console
-errorreport:{ none | prompt | queue | send }
```

## <a name="arguments"></a>Argomenti
 **nessuno**  
 Le segnalazioni sugli errori interni del compilatore non verranno raccolte o inviate a Microsoft.

 **prompt** Richiede di inviare un report quando si riceve un errore interno del compilatore. **prompt** è l'impostazione predefinita se si compila un'applicazione all'interno dell'ambiente di sviluppo.

 **coda** Accoda il rapporto errori. Se si accede con credenziali amministrative, è possibile segnalare qualsiasi errore dall'ultima volta che è stato effettuato l'accesso. Non verrà richiesto di inviare report di errori più di una volta ogni tre giorni. **queue** è l'impostazione predefinita se si compila un'applicazione dalla riga di comando.

 **inviare** Invia automaticamente a Microsoft i rapporti degli errori interni del compilatore. Per abilitare questa opzione, è necessario prima di tutto accettare i Criteri per la raccolta dati Microsoft. La prima volta che si specifica **-errorreport:send** in un computer, viene visualizzato un messaggio del compilatore che indirizza a un sito Web contenente questi criteri.

## <a name="remarks"></a>Osservazioni
 Se il compilatore non è in grado di elaborare un file del codice sorgente, viene restituito un errore interno del compilatore (ICE, Internal Compiler Error). Quando si verifica un ICE, il compilatore non genera né un file di output né informazioni di diagnostica utili per correggere il codice.

 Nelle versioni precedenti, quando si riceveva un ICE si riceveva anche l'invito a contattare il Servizio supporto tecnico Microsoft per segnalare il problema. Con **-errorreport** è possibile offrire informazioni sugli errori interni del compilatore al team Visual C#. Le segnalazioni degli errori consentono di migliorare le versioni future del compilatore.

 La capacità di un utente di inviare report dipende dalle autorizzazioni relative ai criteri utente e computer.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio

1. Aprire la pagina **Proprietà** del progetto. Per altre informazioni, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).

2. Fare clic sulla pagina della proprietà **Compilazione**.

3. Fare clic sul pulsante **Avanzate**.

4. Modificare la proprietà **Segnalazione errori interni del compilatore**.

 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
