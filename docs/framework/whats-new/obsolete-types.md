---
title: Tipi obsoleti in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
ms.openlocfilehash: b7932a553f39e1f1da2a3946878d6224099da8da
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802687"
---
# <a name="obsolete-types-in-the-net-framework"></a>Tipi obsoleti in .NET Framework

<a name="introduction"></a> Nelle tabelle di questo articolo sono elencati i tipi obsoleti in .NET Framework 4.5 e .NET Framework 4.6, organizzati per assembly. Usare i seguenti collegamenti per vedere un elenco di tipi obsoleti e le alternative consigliate in ogni assembly. Poiché questi tipi sono obsoleti, lo sono anche tutti i relativi membri. Per un elenco di altri membri obsoleti nella libreria di classi .NET Framework, vedere [Membri obsoleti](obsolete-members.md).

- [Tipi obsoleti negli assembly di sistema](#obsolete_types_in_system_assemblies)

  - [mscorlib.dll](#mscorlib)

  - [System.Core.dll](#Core)

  - [System.Data.dll](#data)

  - [System.Data.OracleClient.dll](#oracleclient)

  - [System.Design.dll](#design)

  - [System.dll](#system)

  - [System.EnterpriseServices.dll](#enterpriseservices)

  - [System.Net.dll](#net)

  - [System.ServiceModel.dll](#servicemodel)

  - [System.Web.dll](#web)

  - [System.Web.Mobile.dll](#mobile)

  - [System.Workflow.Activities.dll](#workflow_activities)

  - [System.Workflow.ComponentModel.dll](#workflow_componentmodel)

  - [System.Workflow.Runtime.dll](#workflow_runtime)

  - [System.WorkflowServices.dll](#workflowservices)

  - [System.Xaml.dll](#xaml)

  - [System.Xml.dll](#xml)

  - [WindowsBase.dll](#WindowsBase)

- [Tipi obsoleti negli assembly Microsoft](#obsolete_types_in_microsoft_assemblies)

  - [IEHost.dll e IEExec.exe](#IEHost)

  - [Microsoft.Build.Engine.dll](#Engine)

  - [Microsoft.JScript.dll](#jscript)

  - [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)

  - [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)

  - [Microsoft.VisualC.dll](#visualc)

<a name="obsolete_types_in_system_assemblies"></a>

## <a name="obsolete-types-in-system-assemblies"></a>Tipi obsoleti negli assembly di sistema

Nelle seguenti tabelle sono elencati i tipi dichiarati obsoleti negli assembly di sistema. Questi assembly vengono usati per lo sviluppo di applicazioni generiche destinate a .NET Framework.

<a name="mscorlib"></a>

### <a name="assembly-mscorlibdll"></a>Assembly: mscorlib.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.ExecutionEngineException?displayProperty=nameWithType>|Questo tipo indicava in precedenza un errore di runtime irreversibile non specificato. Il runtime non genera più questa eccezione, pertanto il tipo è obsoleto.|
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=nameWithType>|Usare invece <xref:System.StringComparer?displayProperty=nameWithType>.|
|<xref:System.Collections.IHashCodeProvider?displayProperty=nameWithType>|Usare invece <xref:System.Collections.IEqualityComparer?displayProperty=nameWithType>.|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|La classe <xref:System.Configuration.Assemblies.AssemblyHash> è stata deprecata.|
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5. Usare invece la classe <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=nameWithType> nello spazio dei nomi System.Runtime.CompilerServices.|
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=nameWithType>|È disponibile un'API alternativa: creare invece l'attributo personalizzato <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType>|Questo attributo è stato deprecato e sarà rimosso nelle versioni future.|
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType> è stato deprecato.|
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=nameWithType>|Questo attributo è stato deprecato. I domini applicazione non rispettano più i limiti del contesto di attivazione nelle chiamate a IDispatch.|
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=nameWithType>|In alternativa, utilizzare <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=nameWithType>.|
|<xref:System.Security.SecurityCriticalScope?displayProperty=nameWithType>|<xref:System.Security.SecurityCriticalScope> viene usato solo per la compatibilità con la trasparenza di .NET Framework 2.0.|
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=nameWithType>|<xref:System.Security.SecurityTreatAsSafeAttribute> viene usato solo per la compatibilità con la trasparenza di .NET Framework 2.0. In alternativa, usare <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=nameWithType>.|
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=nameWithType>|Questo tipo è obsoleto e sarà rimosso nelle versioni future di .NET Framework.|
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=nameWithType>|La sicurezza dichiarativa a livello di assembly è obsoleta e non viene più applicata da CLR per impostazione predefinita.|
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=nameWithType>|Questo tipo è obsoleto e sarà rimosso nelle versioni future di .NET Framework.|

[Torna all'inizio](#introduction)

<a name="Core"></a>

### <a name="assembly-systemcoredll"></a>Assembly: System.Core.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=nameWithType>|L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Non usare questo tipo.|

[Torna all'inizio](#introduction)

<a name="data"></a>

### <a name="assembly-systemdatadll"></a>Assembly: System.Data.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=nameWithType>|<xref:System.Data.DataSysDescriptionAttribute> è stato deprecato.|
|<xref:System.Data.PropertyAttributes?displayProperty=nameWithType>|<xref:System.Data.PropertyAttributes> è stato deprecato.|
|<xref:System.Data.TypedDataSetGenerator?displayProperty=nameWithType>|La classe <xref:System.Data.TypedDataSetGenerator> sarà rimossa nelle versioni future. Usare <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=nameWithType> in System.Design.dll.|
|<xref:System.Xml.XmlDataDocument?displayProperty=nameWithType>|La classe <xref:System.Xml.XmlDataDocument> sarà rimossa nelle versioni future.|

[Torna all'inizio](#introduction)

<a name="oracleclient"></a>

### <a name="assembly-systemdataoracleclientdll"></a>Assembly: System.Data.OracleClient.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleClientFactory> è stato deprecato.|
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommand> è stato deprecato.|
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommandBuilder> è stato deprecato.|
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnection> è stato deprecato.|
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder> è stato deprecato.|
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleDataAdapter> è stato deprecato.|
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermission> è stato deprecato.|
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType> è stato deprecato.|

[Torna all'inizio](#introduction)

<a name="design"></a>

### <a name="assembly-systemdesigndll"></a>Assembly: System.Design.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=nameWithType>|Questa classe è stata deprecata. In alternativa, utilizzare <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=nameWithType>|Non è consigliabile usare questo tipo in quanto la modifica dei DataBindings viene avviata tramite un oggetto <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType> anziché la griglia delle proprietà.|
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=nameWithType>|Non è consigliabile usare questo tipo in quanto la modifica dei DataBindings viene avviata tramite un oggetto <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType> anziché la griglia delle proprietà.|
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> e <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> e <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=nameWithType>|Non è consigliabile usare questo tipo in quanto la modifica dei modelli è gestita in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Per supportare la modifica dei modelli, esporre i dati dei modelli nella proprietà <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> e chiamare <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=nameWithType>. <xref:System.Web.UI.Design.WebFormsReferenceManager> contiene funzionalità aggiuntive e consente una maggiore estendibilità. Per ottenere <xref:System.Web.UI.Design.WebFormsReferenceManager>, usare la proprietà `RootDesigner.ReferenceManager` da <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=nameWithType>. <xref:System.Web.UI.Design.WebFormsRootDesigner> contiene funzionalità aggiuntive e consente una maggiore estendibilità. Per ottenere <xref:System.Web.UI.Design.WebFormsRootDesigner>, usare la proprietà <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A> da <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=nameWithType>|Non è consigliabile usare questo tipo in quanto la modifica dei modelli è gestita in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Per supportare la modifica dei modelli, esporre i dati dei modelli nella proprietà <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> e chiamare <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=nameWithType>, poiché usa un oggetto <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType> per la modifica del contenuto. Le aree della finestra di progettazione consentono un migliore controllo del contenuto da modificare.|
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=nameWithType>|Non è consigliabile usare questo tipo in quanto la modifica dei modelli è gestita in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Per supportare la modifica dei modelli, esporre i dati dei modelli nella proprietà <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> e chiamare <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=nameWithType>|Non è consigliabile usare questo tipo in quanto la modifica dei modelli è gestita in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Per supportare la modifica dei modelli, esporre i dati dei modelli nella proprietà <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> e chiamare <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=nameWithType>|Non è consigliabile usare questo tipo in quanto la finestra di dialogo Formattazione automatica viene avviata dall'host della finestra di progettazione. L'elenco dei formati automatici disponibili viene esposto in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> nella proprietà <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=nameWithType>, poiché usa un oggetto <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType> per la modifica del contenuto. Le aree della finestra di progettazione consentono un migliore controllo del contenuto da modificare.|

[Torna all'inizio](#introduction)

<a name="system"></a>

### <a name="assembly-systemdll"></a>Assembly: System.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=nameWithType>|Questa interfaccia è stata deprecata. Aggiungere un oggetto <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=nameWithType> per gestire la proprietà <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=nameWithType> del tipo.|
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=nameWithType>|In alternativa, usare <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=nameWithType> per usare il nuovo modello delle impostazioni.|
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=nameWithType>|Questo attributo è stato deprecato. In alternativa, utilizzare <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=nameWithType>.|
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=nameWithType>|Questa classe è stata deprecata.|
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=nameWithType>|Questa classe è stata deprecata. In alternativa, usare i contatori di prestazioni tramite la classe <xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType>.|
|<xref:System.Net.GlobalProxySelection?displayProperty=nameWithType>|Questa classe è stata deprecata. Usare in alternativa <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=nameWithType> per l'accesso e l'impostazione del proxy globale predefinito. Usare "null" anziché <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=nameWithType>.|
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|

[Torna all'inizio](#introduction)

<a name="enterpriseservices"></a>

### <a name="assembly-systementerpriseservicesdll"></a>Assembly: System.EnterpriseServices.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=nameWithType>|La classe <xref:System.EnterpriseServices.RegistrationHelperTx> è stata deprecata.|

[Torna all'inizio](#introduction)

<a name="net"></a>

### <a name="assembly-systemnetdll"></a>Assembly: System.Net.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Net.INetworkProgress?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.UiSynchronizationContext?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|

[Torna all'inizio](#introduction)

<a name="servicemodel"></a>

### <a name="assembly-systemservicemodeldll"></a>Assembly: System.ServiceModel.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> La funzionalità del canale peer è obsoleta e verrà rimossa in futuro.|
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> Questo tipo è obsoleto. Per abilitare l'oggetto <xref:System.Net.CookieContainer> HTTP, usare la proprietà `AllowCookies` nell'associazione HTTP o in <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.|
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> La funzionalità del canale peer è obsoleta e verrà rimossa in futuro.|
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> La funzionalità del canale peer è obsoleta e verrà rimossa in futuro.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> La funzionalità del canale peer è obsoleta e verrà rimossa in futuro.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> La funzionalità del canale peer è obsoleta e verrà rimossa in futuro.|
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> La funzionalità del canale peer è obsoleta e verrà rimossa in futuro.|
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> La funzionalità del canale peer è obsoleta e verrà rimossa in futuro.|

[Torna all'inizio](#introduction)

<a name="web"></a>

### <a name="assembly-systemwebdll"></a>Assembly: System.Web.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=nameWithType>|Questo tipo è obsoleto. Il prodotto di autenticazione Passport non è più supportato ed è stato sostituito dall'[account Microsoft](https://account.microsoft.com/account/Account?destrt=home-index)|
|<xref:System.Web.Mail.MailAttachment?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Net.Mail.Attachment?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailEncoding?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Net.Mime.TransferEncoding?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailFormat?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Net.Mail.MailMessage?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailPriority?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Net.Mail.MailPriority?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.SmtpMail?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>.|
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=nameWithType>|Questo tipo è obsoleto. Il prodotto di autenticazione Passport non è più supportato ed è stato sostituito dall'[account Microsoft](https://account.microsoft.com/account/Account?destrt=home-index)|
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=nameWithType>|Questo tipo è obsoleto. Il prodotto di autenticazione Passport non è più supportato ed è stato sostituito dall'[account Microsoft](https://account.microsoft.com/account/Account?destrt=home-index)|
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=nameWithType>|Questo tipo è obsoleto. Il prodotto di autenticazione Passport non è più supportato ed è stato sostituito dall'[account Microsoft](https://account.microsoft.com/account/Account?destrt=home-index)|
|<xref:System.Web.Security.PassportIdentity?displayProperty=nameWithType>|Questo tipo è obsoleto. Il prodotto di autenticazione Passport non è più supportato ed è stato sostituito dall'[account Microsoft](https://account.microsoft.com/account/Account?destrt=home-index)|
|<xref:System.Web.Security.PassportPrincipal?displayProperty=nameWithType>|Questo tipo è obsoleto. Il prodotto di autenticazione Passport non è più supportato ed è stato sostituito dall'[account Microsoft](https://account.microsoft.com/account/Account?destrt=home-index)|
|<xref:System.Web.UI.ObjectConverter?displayProperty=nameWithType>|L'alternativa consigliata è <xref:System.Convert?displayProperty=nameWithType> e <xref:System.String.Format%2A?displayProperty=nameWithType>.|

[Torna all'inizio](#introduction)

<a name="mobile"></a>

### <a name="assembly-systemwebmobiledll"></a>Assembly: System.Web.Mobile.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Web.Mobile.CookielessData?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Command?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Form?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Image?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Label?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Link?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.List?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Style?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=nameWithType>|L'assembly System.Web.Mobile.dll è stato deprecato e non deve più essere usato. Per informazioni su come sviluppare applicazioni ASP.NET per dispositivi mobili, vedere la pagina su [ASP.NET per dispositivi mobili](/aspnet/mobile/overview).|

[Torna all'inizio](#introduction)

<a name="workflow_activities"></a>

### <a name="assembly-systemworkflowactivitiesdll"></a>Assembly: System.Workflow.Activities.dll

|Tipo di|Message|
|----------|-------------|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.Activities?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|

[Torna all'inizio](#introduction)

<a name="workflow_componentmodel"></a>

### <a name="assembly-systemworkflowcomponentmodeldll"></a>Assembly: System.Workflow.ComponentModel.dll

|Tipo di|Message|
|----------|-------------|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.ComponentModel> fatta eccezione per <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=nameWithType> e <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.ComponentModel.Compiler> fatta eccezione per <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=nameWithType> e <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.ComponentModel.Design> fatta eccezione per <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|

[Torna all'inizio](#introduction)

<a name="workflow_runtime"></a>

### <a name="assembly-systemworkflowruntimedll"></a>Assembly: System.Workflow.Runtime.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Activities.Statements.Interop?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br />I tipi di Workflow Foundation 3.0 sono stati deprecati. Usare invece i nuovi tipi Workflow 4.0 da <xref:System.Activities>\*.|
|<xref:System.Activities.Tracking.InteropTrackingRecord?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br />I tipi di Workflow Foundation 3.0 sono stati deprecati. Usare invece i nuovi tipi Workflow 4.0 da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.Runtime>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.Runtime.Configuration>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.Runtime.DebugEngine> fatta eccezione per <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.Runtime.Hosting> fatta eccezione per <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.Runtime.Tracking>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi System.Workflow.\* sono deprecati. Usare invece i nuovi tipi da <xref:System.Activities>\*.|

[Torna all'inizio](#introduction)

<a name="workflowservices"></a>

### <a name="assembly-systemworkflowservicesdll"></a>Assembly: System.WorkflowServices.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|Tutti i tipi nello spazio dei nomi <xref:System.Workflow.Activities?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> I tipi di WF 3 sono deprecati. Usare invece i nuovi tipi di WF 4 da <xref:System.Activities>\*.|

[Torna all'inizio](#introduction)

<a name="xaml"></a>

### <a name="assembly-systemxamldll"></a>Assembly: System.Xaml.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=nameWithType>|Non viene usato dal parser XAML. Considerare l'utilizzo di <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=nameWithType>.|

[Torna all'inizio](#introduction)

<a name="xml"></a>

### <a name="assembly-systemxmldll"></a>Assembly: System.Xml.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=nameWithType>|Deprecata inizialmente in .NET Framework 4.5.<br /><br /> L'utilizzo di questo tipo genera un errore del compilatore.<br /><br /> Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=nameWithType>|Usare <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> per la compilazione e la convalida dello schema.|
|<xref:System.Xml.XmlValidatingReader?displayProperty=nameWithType>|Usare invece l'oggetto <xref:System.Xml.XmlReader?displayProperty=nameWithType> creato dal metodo <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> mediante l'oggetto <xref:System.Xml.XmlReaderSettings?displayProperty=nameWithType> appropriato.|
|<xref:System.Xml.XmlXapResolver?displayProperty=nameWithType>|L'utilizzo di questo tipo genera un errore del compilatore. Questa API supporta l'infrastruttura .NET Framework e non deve essere utilizzata direttamente dal codice.|
|<xref:System.Xml.Xsl.XslTransform?displayProperty=nameWithType>|Questa classe è stata deprecata. Usare invece <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>.|

[Torna all'inizio](#introduction)

<a name="WindowsBase"></a>

### <a name="assembly-windowsbasedll"></a>Assembly: WindowsBase.dll

|Tipo di|Message|
|----------|-------------|
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType>|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType> è stato deprecato. Questa interfaccia non è più usata.|

[Torna all'inizio](#introduction)

<a name="obsolete_types_in_microsoft_assemblies"></a>

## <a name="obsolete-types-in-microsoft-assemblies"></a>Tipi obsoleti negli assembly Microsoft

Nelle seguenti sezioni sono elencati i tipi obsoleti contenuti negli assembly Microsoft. Questi ultimi sono assembly speciali, ad esempio assembly destinati a un unico linguaggio (es. Microsoft.JScript.dll o Microsoft.VisualC.dll).

<a name="IEHost"></a>

### <a name="assembly-iehostdll-and-ieexecexe"></a>Assembly: IEHost.dll e IEExec.exe

Gli assembly IEHost.dll e IEExec.dll sono stati rimossi da .NET Framework. Tutti i loro tipi e i membri sono obsoleti e non sono supportati a partire da .NET Framework 4. Questi assembly sono usati per eseguire l'hosting dei controlli Windows Form ed eseguire i file eseguibili in Internet Explorer. Le alternative consigliate includono ClickOnce, le applicazioni browser XAML (XBAP) e Microsoft Silverlight.

[Torna all'inizio](#introduction)

<a name="Engine"></a>

### <a name="assembly-microsoftbuildenginedll"></a>Assembly: Microsoft.Build.Engine.dll

|Tipo di|Message|
|----------|-------------|
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=nameWithType>|Questa classe è stata deprecata. Usare invece <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> dall'assembly *Microsoft.Build*.|
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=nameWithType>|Questa classe è stata deprecata. Usare invece <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> dall'assembly *Microsoft.Build*.|

[Torna all'inizio](#introduction)

<a name="jscript"></a>

### <a name="assembly-microsoftjscriptdll"></a>Assembly: Microsoft.JScript.dll

|Tipo di|Message|
|----------|-------------|
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=nameWithType>|Questo tipo è stato deprecato in Visual Studio 2005. Non sono disponibili sostituzioni per questa funzionalità. Per altre informazioni, vedere la documentazione relativa a <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|

[Torna all'inizio](#introduction)

<a name="VBCompat"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydll"></a>Assembly: Microsoft.VisualBasic.Compatibility.dll

Per informazioni sulla migrazione da Visual Basic 6, vedere [Visual Basic 6.0 Resource Center](https://docs.microsoft.com/previous-versions/visualstudio/visual-basic-6/visual-basic-6.0-documentation).

|Tipo di|Message|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=nameWithType>|Questo membro è obsoleto.|

[Torna all'inizio](#introduction)

<a name="VBCompatData"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydatadll"></a>Assembly: Microsoft.VisualBasic.Compatibility.Data.dll

|Tipo di|Message|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=nameWithType>|Questo membro è obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=nameWithType>|Questo membro è obsoleto.|

[Torna all'inizio](#introduction)

<a name="visualc"></a>

### <a name="assembly-microsoftvisualcdll"></a>Assembly: Microsoft.VisualC.dll

|Tipo di|Message|
|----------|-------------|
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll è un assembly obsoleto e viene mantenuto ai soli fini della compatibilità con le versioni precedenti.|

## <a name="see-also"></a>Vedere anche

- [Elementi obsoleti nella libreria di classi](whats-obsolete.md)
- [Membri obsoleti](obsolete-members.md)
