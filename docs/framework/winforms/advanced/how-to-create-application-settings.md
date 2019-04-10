---
title: 'Procedura: Creare impostazioni applicazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
ms.openlocfilehash: 5cf109aec8b55650f43f07f5b303c6373df4efc7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305975"
---
# <a name="how-to-create-application-settings"></a>Procedura: Creare impostazioni applicazione
Usando il codice gestito, è possibile creare nuove impostazioni dell'applicazione e associarle alle proprietà nel form o nei controlli del form, in modo che queste impostazioni vengano caricate e salvate automaticamente in fase di esecuzione.  
  
 Nella routine seguente, viene creata manualmente una classe wrapper che deriva da <xref:System.Configuration.ApplicationSettingsBase>. A questa classe è possibile aggiungere una proprietà accessibile pubblicamente per ogni impostazione dell'applicazione da esporre.  
  
 È anche possibile eseguire questa routine usando la quantità minima di codice nella finestra di progettazione di Visual Studio.  Vedere anche [come: Creare impostazioni dell'applicazione utilizzando la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/wabtadw6(v=vs.100)).  
  
### <a name="to-create-new-application-settings-programmatically"></a>Per creare nuove impostazioni dell'applicazione a livello di codice  
  
1. Aggiungere una nuova classe al progetto e rinominarlo. Per questa procedura, è la classe verrà chiamata `MyUserSettings`. Modificare la definizione della classe in modo che la classe derivi da <xref:System.Configuration.ApplicationSettingsBase>.  
  
2. Definire una proprietà in questa classe wrapper per ogni impostazione dell'applicazione richiesta e applicare la proprietà con <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, in base all'ambito dell'impostazione. Per altre informazioni sull'ambito delle impostazioni, vedere [Application Settings Overview](application-settings-overview.md). A questo punto, il codice dovrebbe risultare simile al seguente:  
  
     [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3. Creare un'istanza della classe wrapper nell'applicazione. Generalmente è un membro privato del form principale. Dopo aver definito la classe, è necessario associarla a una proprietà. In questo caso, la proprietà <xref:System.Windows.Forms.Form.BackColor%2A> del form. È possibile eseguire questa operazione presente nel modulo `Load` gestore dell'evento.  
  
     [!code-csharp[ApplicationSettings.Create#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4. Se si fornisce un modo per modificare le impostazioni in fase di esecuzione, sarà necessario salvare le impostazioni correnti dell'utente su disco quando il form viene chiuso altrimenti le modifiche andranno perse.  
  
     [!code-csharp[ApplicationSettings.Create#3](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     È stata creata una nuova impostazione dell’applicazione, che è stata associata correttamente alla proprietà specificata.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Il provider di impostazioni predefinito, <xref:System.Configuration.LocalFileSettingsProvider>, memorizza le informazioni nei file di configurazione come testo normale. Questo riduce la protezione dell'accesso ai file fornito dal sistema operativo per l'utente corrente. Per questo motivo, è necessario prestare attenzione alle informazioni archiviate nei file di configurazione. Ad esempio, un utilizzo comune per le impostazioni dell'applicazione consiste nell'archiviare le stringhe di connessione che puntano all'archivio dati dell'applicazione. Tuttavia, per motivi di sicurezza, queste stringhe non devono includere le password. Per altre informazioni sulle stringhe di connessione, vedere <xref:System.Configuration.SpecialSetting>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.SpecialSettingAttribute>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
- [Procedura: Convalidare le impostazioni applicazione](how-to-validate-application-settings.md)
