---
title: Accesso ai file e ai dati più sicuro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
ms.openlocfilehash: 49ba1919f68f35e9d72b012540b785e05c307c39
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743757"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="69ac1-102">File e accesso ai dati più sicuri in Windows Form</span><span class="sxs-lookup"><span data-stu-id="69ac1-102">More Secure File and Data Access in Windows Forms</span></span>
<span data-ttu-id="69ac1-103">Il .NET Framework usa le autorizzazioni per proteggere le risorse e i dati.</span><span class="sxs-lookup"><span data-stu-id="69ac1-103">The .NET Framework uses permissions to help protect resources and data.</span></span> <span data-ttu-id="69ac1-104">Il fatto che l'applicazione possa leggere o scrivere dati dipende dalle autorizzazioni concesse all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69ac1-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="69ac1-105">Quando l'applicazione viene eseguita in un ambiente parzialmente attendibile, è possibile che non si riesca ad accedere ai dati oppure potrebbe essere necessario modificare la modalità di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="69ac1-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="69ac1-106">Quando si rileva una restrizione di sicurezza, sono disponibili due opzioni: dichiarare l'autorizzazione (supponendo che sia stata concessa all'applicazione) o usare una versione della funzionalità scritta per operare in caso di attendibilità parziale.</span><span class="sxs-lookup"><span data-stu-id="69ac1-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="69ac1-107">Le sezioni seguenti illustrano come usare il file, il database e l'accesso al Registro di sistema da applicazioni in esecuzione in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="69ac1-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69ac1-108">Per impostazione predefinita, gli strumenti che generano distribuzioni ClickOnce vengono predefiniti per le distribuzioni che richiedono l'attendibilità totale dai computer in cui vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="69ac1-108">By default, tools that generate ClickOnce deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="69ac1-109">Se si decide di voler aggiungere i vantaggi di sicurezza dell'esecuzione in attendibilità parziale, è necessario modificare questa impostazione predefinita in Visual Studio o in uno degli strumenti di Windows SDK (Mage. exe o MageUI. exe).</span><span class="sxs-lookup"><span data-stu-id="69ac1-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either Visual Studio or one of the Windows SDK tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="69ac1-110">Per ulteriori informazioni sulla sicurezza Windows Forms e su come determinare il livello di attendibilità appropriato per l'applicazione, vedere [sicurezza in Windows Forms Panoramica](security-in-windows-forms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="69ac1-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="69ac1-111">Accesso ai file</span><span class="sxs-lookup"><span data-stu-id="69ac1-111">File Access</span></span>  
 <span data-ttu-id="69ac1-112">La classe <xref:System.Security.Permissions.FileIOPermission> controlla l'accesso a file e cartelle nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69ac1-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the .NET Framework.</span></span> <span data-ttu-id="69ac1-113">Per impostazione predefinita, il sistema di sicurezza non concede <xref:System.Security.Permissions.FileIOPermission> agli ambienti con attendibilità parziale, ad esempio la Intranet locale e le aree Internet.</span><span class="sxs-lookup"><span data-stu-id="69ac1-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="69ac1-114">Un'applicazione che richiede l'accesso ai file può comunque funzionare in questi ambienti se si modifica la progettazione dell'applicazione o si usano metodi diversi per accedere ai file.</span><span class="sxs-lookup"><span data-stu-id="69ac1-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="69ac1-115">Per impostazione predefinita, all'area Intranet locale viene concesso il diritto di accesso agli stessi siti e alle stesse directory, di riconnettersi al sito di origine e di leggere dalla directory di installazione.</span><span class="sxs-lookup"><span data-stu-id="69ac1-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="69ac1-116">Per impostazione predefinita, all'area Internet è concesso solo il diritto di riconnettersi al sito di origine.</span><span class="sxs-lookup"><span data-stu-id="69ac1-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="69ac1-117">File specificati dall'utente</span><span class="sxs-lookup"><span data-stu-id="69ac1-117">User-Specified Files</span></span>  
 <span data-ttu-id="69ac1-118">Se non sono disponibili autorizzazioni di accesso ai file, è possibile chiedere all'utente di fornire informazioni specifiche sui file usando la classe <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="69ac1-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="69ac1-119">Questa interazione utente fornisce una discreta garanzia che l'applicazione non possa caricare file riservati o sovrascrivere file importanti in modo intenzionalmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="69ac1-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="69ac1-120">I metodi <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> e <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> forniscono l'accesso ai file in lettura e scrittura aprendo il flusso di file per il file specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="69ac1-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="69ac1-121">I metodi consentono anche di proteggere il file dell'utente nascondendo il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="69ac1-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69ac1-122">Queste autorizzazioni variano a seconda del fatto che l'applicazione sia nell'area Internet o nell'area Intranet.</span><span class="sxs-lookup"><span data-stu-id="69ac1-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="69ac1-123">Le applicazioni dell'area Internet possono usare solo <xref:System.Windows.Forms.OpenFileDialog>, mentre le applicazioni Intranet hanno un'autorizzazione senza restrizioni per le finestre di dialogo per la gestione dei file.</span><span class="sxs-lookup"><span data-stu-id="69ac1-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="69ac1-124">La classe <xref:System.Security.Permissions.FileDialogPermission> specifica il tipo di finestra di dialogo per la gestione dei file che può essere usato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69ac1-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="69ac1-125">La seguente tabella mostra il valore di cui è necessario disporre per usare ogni classe <xref:System.Windows.Forms.FileDialog>.</span><span class="sxs-lookup"><span data-stu-id="69ac1-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="69ac1-126">Classe</span><span class="sxs-lookup"><span data-stu-id="69ac1-126">Class</span></span>|<span data-ttu-id="69ac1-127">Valore di accesso necessario</span><span class="sxs-lookup"><span data-stu-id="69ac1-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
> <span data-ttu-id="69ac1-128">L'autorizzazione specifica viene richiesta solo dopo che il metodo <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> viene effettivamente chiamato.</span><span class="sxs-lookup"><span data-stu-id="69ac1-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="69ac1-129">L'autorizzazione per visualizzare una finestra di dialogo per la gestione dei file non concede all'applicazione l'accesso completo a tutti i membri delle classi <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>e <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="69ac1-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="69ac1-130">Per le autorizzazioni esatte necessarie per chiamare ogni metodo, vedere l'argomento di riferimento per il metodo nella documentazione della libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69ac1-130">For the exact permissions that are required to call each method, see the reference topic for that method in the .NET Framework class library documentation.</span></span>  
  
 <span data-ttu-id="69ac1-131">Il seguente esempio di codice usa il metodo <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> per aprire un file specificato dall'utente in un controllo <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="69ac1-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="69ac1-132">L'esempio richiede <xref:System.Security.Permissions.FileDialogPermission> e il valore dell'enumerazione <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> associata.</span><span class="sxs-lookup"><span data-stu-id="69ac1-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="69ac1-133">L'esempio illustra come gestire <xref:System.Security.SecurityException> per determinare se disabilitare la funzionalità di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="69ac1-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="69ac1-134">Questo esempio richiede che <xref:System.Windows.Forms.Form> disponga di un controllo <xref:System.Windows.Forms.Button> denominato `ButtonOpen` e di un controllo <xref:System.Windows.Forms.RichTextBox> denominato `RtfBoxMain`.</span><span class="sxs-lookup"><span data-stu-id="69ac1-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69ac1-135">La logica di programmazione per la funzionalità di salvataggio non è illustrata nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="69ac1-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click   
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try   
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()   
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try   
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then   
                ' The application does not have unrestricted permission   
                ' to the file so the save feature will be disabled.  
                saveAllowed = False   
            Else   
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)   
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)   
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())   
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try   
        {  
            editingFileName = openFileDialog1.FileName;  
        }   
        catch (Exception ex)   
        {  
            if (ex is System.Security.SecurityException)   
            {  
                // The application does not have unrestricted permission   
                // to the file so the save feature will be disabled.  
                saveAllowed = false;   
            }   
            else   
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="69ac1-136">In visuale C#assicurarsi di aggiungere il codice per abilitare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="69ac1-136">In Visual C#, ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="69ac1-137">Usando il codice dell'esempio precedente, il seguente codice mostra come abilitare il gestore eventi.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span><span class="sxs-lookup"><span data-stu-id="69ac1-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="69ac1-138">Altri file</span><span class="sxs-lookup"><span data-stu-id="69ac1-138">Other Files</span></span>  
 <span data-ttu-id="69ac1-139">Talvolta sarà necessario leggere o scrivere in file non specificati dall'utente, ad esempio quando si devono rendere persistenti le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69ac1-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="69ac1-140">Nelle aree Internet e Intranet locale, l'applicazione non disporrà delle autorizzazioni per archiviare i dati in un file locale.</span><span class="sxs-lookup"><span data-stu-id="69ac1-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="69ac1-141">Tuttavia, l'applicazione potrà archiviare dati nello spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="69ac1-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="69ac1-142">Lo spazio di memorizzazione isolato è un raggruppamento dati astratto, non un percorso di archiviazione specifico, contenente uno o più file dello spazio di memorizzazione isolato, denominati archivi, che includono i percorsi di directory in cui sono effettivamente memorizzati i dati.</span><span class="sxs-lookup"><span data-stu-id="69ac1-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="69ac1-143">Non sono necessarie autorizzazioni di accesso ai file, ad esempio <xref:System.Security.Permissions.FileIOPermission>. La classe <xref:System.Security.Permissions.IsolatedStoragePermission> controlla invece le autorizzazioni per lo spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="69ac1-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="69ac1-144">Per impostazione predefinita, le applicazioni eseguite nelle aree Internet e Intranet locale possono archiviare i dati usando lo spazio di memorizzazione isolato. Tuttavia, le impostazioni come la quota disco possono variare.</span><span class="sxs-lookup"><span data-stu-id="69ac1-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="69ac1-145">Per altre informazioni sullo spazio di memorizzazione isolato, vedere [spazio di memorizzazione isolato](../../standard/io/isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="69ac1-145">For more information about isolated storage, see [Isolated Storage](../../standard/io/isolated-storage.md).</span></span>  
  
 <span data-ttu-id="69ac1-146">L'esempio seguente usa lo spazio di memorizzazione isolato per scrivere dati in un file contenuto in un archivio.</span><span class="sxs-lookup"><span data-stu-id="69ac1-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="69ac1-147">L'esempio richiede <xref:System.Security.Permissions.IsolatedStorageFilePermission> e il valore dell'enumerazione <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>.</span><span class="sxs-lookup"><span data-stu-id="69ac1-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="69ac1-148">L'esempio illustra come leggere e scrivere alcuni valori delle proprietà del controllo <xref:System.Windows.Forms.Button> in un file nello spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="69ac1-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="69ac1-149">La funzione `Read` verrà chiamata dopo l'avvio dell'applicazione e la funzione `Write` verrà chiamata prima della chiusura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69ac1-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="69ac1-150">Nell'esempio è necessario che le funzioni `Read` e `Write` esistano come membri di un <xref:System.Windows.Forms.Form> contenente un controllo <xref:System.Windows.Forms.Button> denominato `MainButton`.</span><span class="sxs-lookup"><span data-stu-id="69ac1-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values   
' for the button if the options file does not exist.  
Public Sub Read()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try   
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _   
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try   
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try   
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _   
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _   
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values   
// for the button if the options file does not exist.  
public void Read()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =   
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try   
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =   
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {   
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }   
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try   
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try   
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new   
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,   
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {   
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="69ac1-151">Accesso database</span><span class="sxs-lookup"><span data-stu-id="69ac1-151">Database Access</span></span>  
 <span data-ttu-id="69ac1-152">Le autorizzazioni necessarie per accedere a un database variano in base al provider del database. Tuttavia, solo le applicazioni in esecuzione con le autorizzazioni appropriate possono accedere a un database tramite una connessione dati.</span><span class="sxs-lookup"><span data-stu-id="69ac1-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="69ac1-153">Per altre informazioni sulle autorizzazioni necessarie per accedere a un database, vedere sicurezza dall' [accesso di codice e ADO.NET](../data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="69ac1-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](../data/adonet/code-access-security.md).</span></span>  
  
 <span data-ttu-id="69ac1-154">Se non è possibile accedere direttamente a un database, perché si desidera che l'applicazione venga eseguita con attendibilità parziale, è possibile usare un servizio Web come alternativa per accedere ai dati.</span><span class="sxs-lookup"><span data-stu-id="69ac1-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="69ac1-155">Un servizio Web è un componente software accessibile a livello di codice in una rete.</span><span class="sxs-lookup"><span data-stu-id="69ac1-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="69ac1-156">Con i servizi Web, le applicazioni possono condividere dati tra le aree dei gruppi di codice.</span><span class="sxs-lookup"><span data-stu-id="69ac1-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="69ac1-157">Per impostazione predefinita, alle applicazioni nelle aree Internet e Intranet locale viene concesso il diritto di accedere ai relativi siti di origine. Questo consente a tali applicazioni di chiamare un servizio Web ospitato nello stesso server.</span><span class="sxs-lookup"><span data-stu-id="69ac1-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="69ac1-158">Per altre informazioni, vedere [servizi Web in ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) o [Windows Communication Foundation](../wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="69ac1-158">For more information see [Web Services in ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) or [Windows Communication Foundation](../wcf/index.md).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="69ac1-159">Accesso al Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="69ac1-159">Registry Access</span></span>  
 <span data-ttu-id="69ac1-160">La classe <xref:System.Security.Permissions.RegistryPermission> controlla l'accesso al Registro di sistema del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="69ac1-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="69ac1-161">Per impostazione predefinita, solo le applicazioni in esecuzione in locale possono accedere al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="69ac1-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="69ac1-162"><xref:System.Security.Permissions.RegistryPermission> concede a un'applicazione solo il diritto di provare ad accedere al Registro di sistema. Non garantisce l'accesso, perché il sistema operativo continua ad applicare la sicurezza al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="69ac1-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="69ac1-163">Poiché non è possibile accedere al Registro di sistema con l'attendibilità parziale, potrebbe essere necessario trovare altri metodi di archiviazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="69ac1-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="69ac1-164">Quando si archiviano le impostazioni dell'applicazione, usare lo spazio di memorizzazione isolato invece del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="69ac1-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="69ac1-165">Lo spazio di memorizzazione isolato può essere usato anche per archiviare altri file specifici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69ac1-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="69ac1-166">È anche possibile archiviare informazioni di applicazioni globali relative al server o al sito di origine, perché, per impostazione predefinita, a un'applicazione viene concesso il diritto di accedere al sito di origine.</span><span class="sxs-lookup"><span data-stu-id="69ac1-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ac1-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69ac1-167">See also</span></span>

- [<span data-ttu-id="69ac1-168">Stampa più sicura in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69ac1-168">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)
- [<span data-ttu-id="69ac1-169">Considerazioni aggiuntive sulla sicurezza in Windows Form</span><span class="sxs-lookup"><span data-stu-id="69ac1-169">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="69ac1-170">Panoramica della sicurezza in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69ac1-170">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="69ac1-171">Sicurezza di Windows Form</span><span class="sxs-lookup"><span data-stu-id="69ac1-171">Windows Forms Security</span></span>](windows-forms-security.md)
- [<span data-ttu-id="69ac1-172">Mage.exe (Strumento per la generazione e la modifica di manifesti)</span><span class="sxs-lookup"><span data-stu-id="69ac1-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../tools/mage-exe-manifest-generation-and-editing-tool.md)
- [<span data-ttu-id="69ac1-173">MageUI.exe (Strumento per la generazione e la modifica di manifesti, client grafico)</span><span class="sxs-lookup"><span data-stu-id="69ac1-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
