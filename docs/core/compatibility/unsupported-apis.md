---
title: API non supportate in .NET Core
titleSuffix: ''
description: Informazioni sulle API di .NET Framework che generano sempre un'eccezione in .NET Core.Learn which APIs from the .NET Framework that always throw an exception on .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: bd3516d9480ef42b6ea89825ba64867a3ca104e3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242946"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="93ec2-103">API che generano sempre eccezioni in .NET Core</span><span class="sxs-lookup"><span data-stu-id="93ec2-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="93ec2-104">Le API seguenti genereranno <xref:System.PlatformNotSupportedException> sempre un'eccezione in .NET Core in tutte o in un sottoinsieme di piattaforme.</span><span class="sxs-lookup"><span data-stu-id="93ec2-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="93ec2-105">Questo articolo organizza i membri API interessati per spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="93ec2-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="93ec2-106">Questo articolo è un work-in-progress.</span><span class="sxs-lookup"><span data-stu-id="93ec2-106">This article is a work-in-progress.</span></span> <span data-ttu-id="93ec2-107">Non è un elenco completo di API che generano eccezioni in .NET Core.It is not a complete list of APIs that throw exceptions on .NET Core.</span><span class="sxs-lookup"><span data-stu-id="93ec2-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="93ec2-108">In questo articolo non sono incluse le implementazioni esplicite dell'interfaccia per la serializzazione binaria che generano .NET Core.This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span><span class="sxs-lookup"><span data-stu-id="93ec2-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="93ec2-109">Per ulteriori informazioni, vedere [Serializzazione binaria in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="93ec2-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="93ec2-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="93ec2-110">System</span></span>

| <span data-ttu-id="93ec2-111">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-111">Member</span></span> | <span data-ttu-id="93ec2-112">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-113">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="93ec2-115">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="93ec2-116">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-117">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="93ec2-118">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="93ec2-119">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="93ec2-120">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-121">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-122">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="93ec2-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="93ec2-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="93ec2-124">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-124">Member</span></span> | <span data-ttu-id="93ec2-125">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-126">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-127">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-128">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="93ec2-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="93ec2-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="93ec2-130">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-130">Member</span></span> | <span data-ttu-id="93ec2-131">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-132">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-133">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-134">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="93ec2-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="93ec2-135">System.Configuration</span></span>

| <span data-ttu-id="93ec2-136">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-136">Member</span></span> | <span data-ttu-id="93ec2-137">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="93ec2-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="93ec2-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="93ec2-139">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="93ec2-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="93ec2-140">System.Console</span></span>

| <span data-ttu-id="93ec2-141">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-141">Member</span></span> | <span data-ttu-id="93ec2-142">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="93ec2-143">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-143">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-145">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-145">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-147">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-147">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-149">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-149">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>(solo per quanto fa)</span><span class="sxs-lookup"><span data-stu-id="93ec2-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="93ec2-151">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-152">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-153">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-154">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-154">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-155"><xref:System.Console.Title?displayProperty=nameWithType>(solo per quanto fa)</span><span class="sxs-lookup"><span data-stu-id="93ec2-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="93ec2-156">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-156">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-158">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-158">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-160">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-160">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-162">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-162">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-164">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="93ec2-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="93ec2-165">System.Data.Common</span></span>

| <span data-ttu-id="93ec2-166">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-166">Member</span></span> | <span data-ttu-id="93ec2-167">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="93ec2-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType><xref:System.NotSupportedException>(lanci)</span><span class="sxs-lookup"><span data-stu-id="93ec2-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="93ec2-169">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="93ec2-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="93ec2-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="93ec2-171">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-171">Member</span></span> | <span data-ttu-id="93ec2-172">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="93ec2-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-174">Linux</span><span class="sxs-lookup"><span data-stu-id="93ec2-174">Linux</span></span> |
| <span data-ttu-id="93ec2-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-176">Linux</span><span class="sxs-lookup"><span data-stu-id="93ec2-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="93ec2-177">macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="93ec2-178">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-179">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="93ec2-180">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="93ec2-181">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="93ec2-182">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="93ec2-183">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-183">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-185">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-185">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(solo per quanto fa)</span><span class="sxs-lookup"><span data-stu-id="93ec2-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="93ec2-187">macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-187">macOS</span></span> |
| <span data-ttu-id="93ec2-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-189">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="93ec2-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="93ec2-190">System.IO</span></span>

| <span data-ttu-id="93ec2-191">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-191">Member</span></span> | <span data-ttu-id="93ec2-192">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-193">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-194">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="93ec2-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="93ec2-195">System.IO.Pipes</span></span>

| <span data-ttu-id="93ec2-196">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-196">Member</span></span> | <span data-ttu-id="93ec2-197">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="93ec2-198">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="93ec2-199">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="93ec2-200">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="93ec2-201">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-201">Linux and macOS</span></span> |
| <span data-ttu-id="93ec2-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-203">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="93ec2-204">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="93ec2-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="93ec2-205">System.Media</span></span>

| <span data-ttu-id="93ec2-206">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-206">Member</span></span> | <span data-ttu-id="93ec2-207">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-208">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="93ec2-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="93ec2-209">System.Net</span></span>

| <span data-ttu-id="93ec2-210">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-210">Member</span></span> | <span data-ttu-id="93ec2-211">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-212">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-213">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-214">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-215">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-216">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-217">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-218">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-219">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-220">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-221">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-222">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="93ec2-223">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-224">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-225">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-226">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-227">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-228">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="93ec2-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="93ec2-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="93ec2-230">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-230">Member</span></span> | <span data-ttu-id="93ec2-231">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="93ec2-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="93ec2-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="93ec2-233">System.Net.Sockets</span></span>

| <span data-ttu-id="93ec2-234">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-234">Member</span></span> | <span data-ttu-id="93ec2-235">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="93ec2-236">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-237">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="93ec2-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="93ec2-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="93ec2-239">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-239">Member</span></span> | <span data-ttu-id="93ec2-240">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="93ec2-241">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="93ec2-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="93ec2-242">System.Reflection</span></span>

| <span data-ttu-id="93ec2-243">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-243">Member</span></span> | <span data-ttu-id="93ec2-244">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-245">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-246">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-247">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-248">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="93ec2-249">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-250">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="93ec2-251">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="93ec2-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="93ec2-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="93ec2-253">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-253">Member</span></span> | <span data-ttu-id="93ec2-254">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="93ec2-255">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="93ec2-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="93ec2-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="93ec2-257">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-257">Member</span></span> | <span data-ttu-id="93ec2-258">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-259">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="93ec2-260">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-261">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-262">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-263">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-264">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-265">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="93ec2-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="93ec2-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="93ec2-267">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-267">Member</span></span> | <span data-ttu-id="93ec2-268">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="93ec2-269">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="93ec2-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="93ec2-270">System.Security</span></span>

| <span data-ttu-id="93ec2-271">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-271">Member</span></span> | <span data-ttu-id="93ec2-272">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="93ec2-273">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="93ec2-274">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-275">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="93ec2-276">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="93ec2-277">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="93ec2-278">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="93ec2-279">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="93ec2-280">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="93ec2-281">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="93ec2-282">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="93ec2-283">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-284">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="93ec2-285">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="93ec2-286">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="93ec2-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="93ec2-287">System.Security.Claims</span></span>

| <span data-ttu-id="93ec2-288">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-288">Member</span></span> | <span data-ttu-id="93ec2-289">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="93ec2-290">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-291">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="93ec2-292">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-293">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-294">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="93ec2-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="93ec2-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="93ec2-296">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-296">Member</span></span> | <span data-ttu-id="93ec2-297">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-298">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="93ec2-299">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="93ec2-300">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="93ec2-301">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="93ec2-302">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="93ec2-303">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="93ec2-304">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="93ec2-305">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="93ec2-306">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="93ec2-307">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="93ec2-308">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="93ec2-309">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="93ec2-310">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="93ec2-311">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="93ec2-312">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="93ec2-313">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-314">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-315">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-316">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-317">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="93ec2-318">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-319">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-320">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-321">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="93ec2-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-322">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-323">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="93ec2-324">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-325">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="93ec2-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="93ec2-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="93ec2-327">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-327">Member</span></span> | <span data-ttu-id="93ec2-328">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="93ec2-329">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-330">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="93ec2-331">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="93ec2-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="93ec2-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="93ec2-333">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-333">Member</span></span> | <span data-ttu-id="93ec2-334">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-335">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-336">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-337">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-337">All</span></span> |
| <span data-ttu-id="93ec2-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(solo set)</span><span class="sxs-lookup"><span data-stu-id="93ec2-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="93ec2-339">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="93ec2-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="93ec2-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="93ec2-341">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-341">Member</span></span> | <span data-ttu-id="93ec2-342">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-343">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="93ec2-344">System.security.policy</span><span class="sxs-lookup"><span data-stu-id="93ec2-344">System.Security.Policy</span></span>

| <span data-ttu-id="93ec2-345">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-345">Member</span></span> | <span data-ttu-id="93ec2-346">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-347">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="93ec2-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="93ec2-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="93ec2-349">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-349">Member</span></span> | <span data-ttu-id="93ec2-350">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="93ec2-351">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="93ec2-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="93ec2-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="93ec2-353">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-353">Member</span></span> | <span data-ttu-id="93ec2-354">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-355">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="93ec2-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="93ec2-356">System.Threading</span></span>

| <span data-ttu-id="93ec2-357">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-357">Member</span></span> | <span data-ttu-id="93ec2-358">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-359">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-360">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="93ec2-361">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="93ec2-362">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="93ec2-363">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="93ec2-364">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="93ec2-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="93ec2-365">System.Xml</span></span>

| <span data-ttu-id="93ec2-366">Membro</span><span class="sxs-lookup"><span data-stu-id="93ec2-366">Member</span></span> | <span data-ttu-id="93ec2-367">Piattaforme che lanciano</span><span class="sxs-lookup"><span data-stu-id="93ec2-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-368">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-369">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="93ec2-370">Tutti</span><span class="sxs-lookup"><span data-stu-id="93ec2-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="93ec2-371">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93ec2-371">See also</span></span>

- [<span data-ttu-id="93ec2-372">Modifiche di rilievo per la migrazione da .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="93ec2-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="93ec2-373">Serializzazione binaria in .NET Core</span><span class="sxs-lookup"><span data-stu-id="93ec2-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="93ec2-374">Analizzatore di portabilità .NET</span><span class="sxs-lookup"><span data-stu-id="93ec2-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
