---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783443"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="95731-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="95731-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="95731-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="95731-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="95731-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="95731-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="95731-105">Il driver Microsoft SQL Server OLE DB supporta le seguenti raccolte di schemi specifici, oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="95731-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="95731-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="95731-106">Tables</span></span>  
  
- <span data-ttu-id="95731-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="95731-107">Columns</span></span>  
  
- <span data-ttu-id="95731-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="95731-108">Procedures</span></span>  
  
- <span data-ttu-id="95731-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="95731-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="95731-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="95731-110">Catalog</span></span>  
  
- <span data-ttu-id="95731-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="95731-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="95731-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="95731-112">Tables</span></span>  
  
|<span data-ttu-id="95731-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-113">ColumnName</span></span>|<span data-ttu-id="95731-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-115">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-116">String</span><span class="sxs-lookup"><span data-stu-id="95731-116">String</span></span>|  
|<span data-ttu-id="95731-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-118">String</span><span class="sxs-lookup"><span data-stu-id="95731-118">String</span></span>|  
|<span data-ttu-id="95731-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-119">TABLE_NAME</span></span>|<span data-ttu-id="95731-120">String</span><span class="sxs-lookup"><span data-stu-id="95731-120">String</span></span>|  
|<span data-ttu-id="95731-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-121">TABLE_TYPE</span></span>|<span data-ttu-id="95731-122">String</span><span class="sxs-lookup"><span data-stu-id="95731-122">String</span></span>|  
|<span data-ttu-id="95731-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-123">TABLE_GUID</span></span>|<span data-ttu-id="95731-124">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-124">Guid</span></span>|  
|<span data-ttu-id="95731-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-125">DESCRIPTION</span></span>|<span data-ttu-id="95731-126">String</span><span class="sxs-lookup"><span data-stu-id="95731-126">String</span></span>|  
|<span data-ttu-id="95731-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-127">TABLE_PROPID</span></span>|<span data-ttu-id="95731-128">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-128">Int64</span></span>|  
|<span data-ttu-id="95731-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-129">DATE_CREATED</span></span>|<span data-ttu-id="95731-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-130">DateTime</span></span>|  
|<span data-ttu-id="95731-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-131">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="95731-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="95731-133">Columns</span></span>  
  
|<span data-ttu-id="95731-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-134">ColumnName</span></span>|<span data-ttu-id="95731-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-136">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-137">String</span><span class="sxs-lookup"><span data-stu-id="95731-137">String</span></span>|  
|<span data-ttu-id="95731-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-139">String</span><span class="sxs-lookup"><span data-stu-id="95731-139">String</span></span>|  
|<span data-ttu-id="95731-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-140">TABLE_NAME</span></span>|<span data-ttu-id="95731-141">String</span><span class="sxs-lookup"><span data-stu-id="95731-141">String</span></span>|  
|<span data-ttu-id="95731-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-142">COLUMN_NAME</span></span>|<span data-ttu-id="95731-143">String</span><span class="sxs-lookup"><span data-stu-id="95731-143">String</span></span>|  
|<span data-ttu-id="95731-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-144">COLUMN_GUID</span></span>|<span data-ttu-id="95731-145">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-145">Guid</span></span>|  
|<span data-ttu-id="95731-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-146">COLUMN_PROPID</span></span>|<span data-ttu-id="95731-147">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-147">Int64</span></span>|  
|<span data-ttu-id="95731-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-149">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-149">Int64</span></span>|  
|<span data-ttu-id="95731-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="95731-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-151">Boolean</span></span>|  
|<span data-ttu-id="95731-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="95731-153">String</span><span class="sxs-lookup"><span data-stu-id="95731-153">String</span></span>|  
|<span data-ttu-id="95731-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="95731-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="95731-155">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-155">Int64</span></span>|  
|<span data-ttu-id="95731-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="95731-156">IS_NULLABLE</span></span>|<span data-ttu-id="95731-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-157">Boolean</span></span>|  
|<span data-ttu-id="95731-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-158">DATA_TYPE</span></span>|<span data-ttu-id="95731-159">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-159">Int32</span></span>|  
|<span data-ttu-id="95731-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-160">TYPE_GUID</span></span>|<span data-ttu-id="95731-161">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-161">Guid</span></span>|  
|<span data-ttu-id="95731-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="95731-163">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-163">Int64</span></span>|  
|<span data-ttu-id="95731-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="95731-165">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-165">Int64</span></span>|  
|<span data-ttu-id="95731-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="95731-167">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-167">Int32</span></span>|  
|<span data-ttu-id="95731-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="95731-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="95731-169">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-169">Int16</span></span>|  
|<span data-ttu-id="95731-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="95731-171">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-171">Int64</span></span>|  
|<span data-ttu-id="95731-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="95731-173">String</span><span class="sxs-lookup"><span data-stu-id="95731-173">String</span></span>|  
|<span data-ttu-id="95731-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="95731-175">String</span><span class="sxs-lookup"><span data-stu-id="95731-175">String</span></span>|  
|<span data-ttu-id="95731-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="95731-177">String</span><span class="sxs-lookup"><span data-stu-id="95731-177">String</span></span>|  
|<span data-ttu-id="95731-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="95731-179">String</span><span class="sxs-lookup"><span data-stu-id="95731-179">String</span></span>|  
|<span data-ttu-id="95731-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="95731-181">String</span><span class="sxs-lookup"><span data-stu-id="95731-181">String</span></span>|  
|<span data-ttu-id="95731-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-182">COLLATION_NAME</span></span>|<span data-ttu-id="95731-183">String</span><span class="sxs-lookup"><span data-stu-id="95731-183">String</span></span>|  
|<span data-ttu-id="95731-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="95731-185">String</span><span class="sxs-lookup"><span data-stu-id="95731-185">String</span></span>|  
|<span data-ttu-id="95731-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="95731-187">String</span><span class="sxs-lookup"><span data-stu-id="95731-187">String</span></span>|  
|<span data-ttu-id="95731-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-188">DOMAIN_NAME</span></span>|<span data-ttu-id="95731-189">String</span><span class="sxs-lookup"><span data-stu-id="95731-189">String</span></span>|  
|<span data-ttu-id="95731-190">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-190">DESCRIPTION</span></span>|<span data-ttu-id="95731-191">String</span><span class="sxs-lookup"><span data-stu-id="95731-191">String</span></span>|  
|<span data-ttu-id="95731-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="95731-192">COLUMN_LCID</span></span>|<span data-ttu-id="95731-193">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-193">Int32</span></span>|  
|<span data-ttu-id="95731-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="95731-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="95731-195">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-195">Int32</span></span>|  
|<span data-ttu-id="95731-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="95731-196">COLUMN_SORTID</span></span>|<span data-ttu-id="95731-197">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-197">Int32</span></span>|  
|<span data-ttu-id="95731-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="95731-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="95731-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="95731-199">Byte[]</span></span>|  
|<span data-ttu-id="95731-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="95731-200">IS_COMPUTED</span></span>|<span data-ttu-id="95731-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="95731-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="95731-202">Procedures</span></span>  
  
|<span data-ttu-id="95731-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-203">ColumnName</span></span>|<span data-ttu-id="95731-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="95731-206">String</span><span class="sxs-lookup"><span data-stu-id="95731-206">String</span></span>|  
|<span data-ttu-id="95731-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="95731-208">String</span><span class="sxs-lookup"><span data-stu-id="95731-208">String</span></span>|  
|<span data-ttu-id="95731-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="95731-210">String</span><span class="sxs-lookup"><span data-stu-id="95731-210">String</span></span>|  
|<span data-ttu-id="95731-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="95731-212">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-212">Int16</span></span>|  
|<span data-ttu-id="95731-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="95731-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="95731-214">String</span><span class="sxs-lookup"><span data-stu-id="95731-214">String</span></span>|  
|<span data-ttu-id="95731-215">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-215">DESCRIPTION</span></span>|<span data-ttu-id="95731-216">String</span><span class="sxs-lookup"><span data-stu-id="95731-216">String</span></span>|  
|<span data-ttu-id="95731-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-217">DATE_CREATED</span></span>|<span data-ttu-id="95731-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-218">DateTime</span></span>|  
|<span data-ttu-id="95731-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-219">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="95731-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="95731-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="95731-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-222">ColumnName</span></span>|<span data-ttu-id="95731-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="95731-225">String</span><span class="sxs-lookup"><span data-stu-id="95731-225">String</span></span>|  
|<span data-ttu-id="95731-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="95731-227">String</span><span class="sxs-lookup"><span data-stu-id="95731-227">String</span></span>|  
|<span data-ttu-id="95731-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="95731-229">String</span><span class="sxs-lookup"><span data-stu-id="95731-229">String</span></span>|  
|<span data-ttu-id="95731-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-230">PARAMETER_NAME</span></span>|<span data-ttu-id="95731-231">String</span><span class="sxs-lookup"><span data-stu-id="95731-231">String</span></span>|  
|<span data-ttu-id="95731-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-233">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-233">Int32</span></span>|  
|<span data-ttu-id="95731-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="95731-235">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-235">Int32</span></span>|  
|<span data-ttu-id="95731-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="95731-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-237">Boolean</span></span>|  
|<span data-ttu-id="95731-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="95731-239">String</span><span class="sxs-lookup"><span data-stu-id="95731-239">String</span></span>|  
|<span data-ttu-id="95731-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="95731-240">IS_NULLABLE</span></span>|<span data-ttu-id="95731-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-241">Boolean</span></span>|  
|<span data-ttu-id="95731-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-242">DATA_TYPE</span></span>|<span data-ttu-id="95731-243">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-243">Int32</span></span>|  
|<span data-ttu-id="95731-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="95731-245">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-245">Int64</span></span>|  
|<span data-ttu-id="95731-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="95731-247">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-247">Int64</span></span>|  
|<span data-ttu-id="95731-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="95731-249">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-249">Int32</span></span>|  
|<span data-ttu-id="95731-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="95731-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="95731-251">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-251">Int16</span></span>|  
|<span data-ttu-id="95731-252">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-252">DESCRIPTION</span></span>|<span data-ttu-id="95731-253">String</span><span class="sxs-lookup"><span data-stu-id="95731-253">String</span></span>|  
|<span data-ttu-id="95731-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-254">TYPE_NAME</span></span>|<span data-ttu-id="95731-255">String</span><span class="sxs-lookup"><span data-stu-id="95731-255">String</span></span>|  
|<span data-ttu-id="95731-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="95731-257">String</span><span class="sxs-lookup"><span data-stu-id="95731-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="95731-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="95731-258">Catalog</span></span>  
  
|<span data-ttu-id="95731-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-259">ColumnName</span></span>|<span data-ttu-id="95731-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-261">CATALOG_NAME</span></span>|<span data-ttu-id="95731-262">String</span><span class="sxs-lookup"><span data-stu-id="95731-262">String</span></span>|  
|<span data-ttu-id="95731-263">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-263">DESCRIPTION</span></span>|<span data-ttu-id="95731-264">String</span><span class="sxs-lookup"><span data-stu-id="95731-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="95731-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="95731-265">Indexes</span></span>  
  
|<span data-ttu-id="95731-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-266">ColumnName</span></span>|<span data-ttu-id="95731-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-268">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-269">String</span><span class="sxs-lookup"><span data-stu-id="95731-269">String</span></span>|  
|<span data-ttu-id="95731-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-271">String</span><span class="sxs-lookup"><span data-stu-id="95731-271">String</span></span>|  
|<span data-ttu-id="95731-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-272">TABLE_NAME</span></span>|<span data-ttu-id="95731-273">String</span><span class="sxs-lookup"><span data-stu-id="95731-273">String</span></span>|  
|<span data-ttu-id="95731-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-274">INDEX_CATALOG</span></span>|<span data-ttu-id="95731-275">String</span><span class="sxs-lookup"><span data-stu-id="95731-275">String</span></span>|  
|<span data-ttu-id="95731-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="95731-277">String</span><span class="sxs-lookup"><span data-stu-id="95731-277">String</span></span>|  
|<span data-ttu-id="95731-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-278">INDEX_NAME</span></span>|<span data-ttu-id="95731-279">String</span><span class="sxs-lookup"><span data-stu-id="95731-279">String</span></span>|  
|<span data-ttu-id="95731-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="95731-280">PRIMARY_KEY</span></span>|<span data-ttu-id="95731-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-281">Boolean</span></span>|  
|<span data-ttu-id="95731-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="95731-282">UNIQUE</span></span>|<span data-ttu-id="95731-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-283">Boolean</span></span>|  
|<span data-ttu-id="95731-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="95731-284">CLUSTERED</span></span>|<span data-ttu-id="95731-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-285">Boolean</span></span>|  
|<span data-ttu-id="95731-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-286">TYPE</span></span>|<span data-ttu-id="95731-287">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-287">Int32</span></span>|  
|<span data-ttu-id="95731-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="95731-288">FILL_FACTOR</span></span>|<span data-ttu-id="95731-289">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-289">Int32</span></span>|  
|<span data-ttu-id="95731-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="95731-290">INITIAL_SIZE</span></span>|<span data-ttu-id="95731-291">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-291">Int32</span></span>|  
|<span data-ttu-id="95731-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="95731-292">NULLS</span></span>|<span data-ttu-id="95731-293">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-293">Int32</span></span>|  
|<span data-ttu-id="95731-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="95731-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="95731-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-295">Boolean</span></span>|  
|<span data-ttu-id="95731-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="95731-296">AUTO_UPDATE</span></span>|<span data-ttu-id="95731-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-297">Boolean</span></span>|  
|<span data-ttu-id="95731-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="95731-298">NULL_COLLATION</span></span>|<span data-ttu-id="95731-299">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-299">Int32</span></span>|  
|<span data-ttu-id="95731-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-301">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-301">Int64</span></span>|  
|<span data-ttu-id="95731-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-302">COLUMN_NAME</span></span>|<span data-ttu-id="95731-303">String</span><span class="sxs-lookup"><span data-stu-id="95731-303">String</span></span>|  
|<span data-ttu-id="95731-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-304">COLUMN_GUID</span></span>|<span data-ttu-id="95731-305">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-305">Guid</span></span>|  
|<span data-ttu-id="95731-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-306">COLUMN_PROPID</span></span>|<span data-ttu-id="95731-307">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-307">Int64</span></span>|  
|<span data-ttu-id="95731-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="95731-308">COLLATION</span></span>|<span data-ttu-id="95731-309">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-309">Int16</span></span>|  
|<span data-ttu-id="95731-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="95731-310">CARDINALITY</span></span>|<span data-ttu-id="95731-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="95731-311">Decimal</span></span>|  
|<span data-ttu-id="95731-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="95731-312">PAGES</span></span>|<span data-ttu-id="95731-313">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-313">Int32</span></span>|  
|<span data-ttu-id="95731-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="95731-314">FILTER_CONDITION</span></span>|<span data-ttu-id="95731-315">String</span><span class="sxs-lookup"><span data-stu-id="95731-315">String</span></span>|  
|<span data-ttu-id="95731-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="95731-316">INTEGRATED</span></span>|<span data-ttu-id="95731-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="95731-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="95731-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="95731-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="95731-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="95731-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="95731-320">Tables</span></span>  
  
- <span data-ttu-id="95731-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="95731-321">Columns</span></span>  
  
- <span data-ttu-id="95731-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="95731-322">Procedures</span></span>  
  
- <span data-ttu-id="95731-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="95731-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="95731-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="95731-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="95731-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="95731-325">Views</span></span>  
  
- <span data-ttu-id="95731-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="95731-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="95731-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="95731-327">Tables</span></span>  
  
|<span data-ttu-id="95731-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-328">ColumnName</span></span>|<span data-ttu-id="95731-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-330">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-331">String</span><span class="sxs-lookup"><span data-stu-id="95731-331">String</span></span>|  
|<span data-ttu-id="95731-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-333">String</span><span class="sxs-lookup"><span data-stu-id="95731-333">String</span></span>|  
|<span data-ttu-id="95731-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-334">TABLE_NAME</span></span>|<span data-ttu-id="95731-335">String</span><span class="sxs-lookup"><span data-stu-id="95731-335">String</span></span>|  
|<span data-ttu-id="95731-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-336">TABLE_TYPE</span></span>|<span data-ttu-id="95731-337">String</span><span class="sxs-lookup"><span data-stu-id="95731-337">String</span></span>|  
|<span data-ttu-id="95731-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-338">TABLE_GUID</span></span>|<span data-ttu-id="95731-339">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-339">Guid</span></span>|  
|<span data-ttu-id="95731-340">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-340">DESCRIPTION</span></span>|<span data-ttu-id="95731-341">String</span><span class="sxs-lookup"><span data-stu-id="95731-341">String</span></span>|  
|<span data-ttu-id="95731-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-342">TABLE_PROPID</span></span>|<span data-ttu-id="95731-343">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-343">Int64</span></span>|  
|<span data-ttu-id="95731-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-344">DATE_CREATED</span></span>|<span data-ttu-id="95731-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-345">DateTime</span></span>|  
|<span data-ttu-id="95731-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-346">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="95731-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="95731-348">Columns</span></span>  
  
|<span data-ttu-id="95731-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-349">ColumnName</span></span>|<span data-ttu-id="95731-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-351">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-352">String</span><span class="sxs-lookup"><span data-stu-id="95731-352">String</span></span>|  
|<span data-ttu-id="95731-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-354">String</span><span class="sxs-lookup"><span data-stu-id="95731-354">String</span></span>|  
|<span data-ttu-id="95731-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-355">TABLE_NAME</span></span>|<span data-ttu-id="95731-356">String</span><span class="sxs-lookup"><span data-stu-id="95731-356">String</span></span>|  
|<span data-ttu-id="95731-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-357">COLUMN_NAME</span></span>|<span data-ttu-id="95731-358">String</span><span class="sxs-lookup"><span data-stu-id="95731-358">String</span></span>|  
|<span data-ttu-id="95731-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-359">COLUMN_GUID</span></span>|<span data-ttu-id="95731-360">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-360">Guid</span></span>|  
|<span data-ttu-id="95731-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-361">COLUMN_PROPID</span></span>|<span data-ttu-id="95731-362">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-362">Int64</span></span>|  
|<span data-ttu-id="95731-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-364">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-364">Int64</span></span>|  
|<span data-ttu-id="95731-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="95731-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-366">Boolean</span></span>|  
|<span data-ttu-id="95731-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="95731-368">String</span><span class="sxs-lookup"><span data-stu-id="95731-368">String</span></span>|  
|<span data-ttu-id="95731-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="95731-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="95731-370">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-370">Int64</span></span>|  
|<span data-ttu-id="95731-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="95731-371">IS_NULLABLE</span></span>|<span data-ttu-id="95731-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-372">Boolean</span></span>|  
|<span data-ttu-id="95731-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-373">DATA_TYPE</span></span>|<span data-ttu-id="95731-374">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-374">Int32</span></span>|  
|<span data-ttu-id="95731-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-375">TYPE_GUID</span></span>|<span data-ttu-id="95731-376">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-376">Guid</span></span>|  
|<span data-ttu-id="95731-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="95731-378">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-378">Int64</span></span>|  
|<span data-ttu-id="95731-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="95731-380">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-380">Int64</span></span>|  
|<span data-ttu-id="95731-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="95731-382">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-382">Int32</span></span>|  
|<span data-ttu-id="95731-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="95731-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="95731-384">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-384">Int16</span></span>|  
|<span data-ttu-id="95731-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="95731-386">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-386">Int64</span></span>|  
|<span data-ttu-id="95731-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="95731-388">String</span><span class="sxs-lookup"><span data-stu-id="95731-388">String</span></span>|  
|<span data-ttu-id="95731-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="95731-390">String</span><span class="sxs-lookup"><span data-stu-id="95731-390">String</span></span>|  
|<span data-ttu-id="95731-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="95731-392">String</span><span class="sxs-lookup"><span data-stu-id="95731-392">String</span></span>|  
|<span data-ttu-id="95731-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="95731-394">String</span><span class="sxs-lookup"><span data-stu-id="95731-394">String</span></span>|  
|<span data-ttu-id="95731-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="95731-396">String</span><span class="sxs-lookup"><span data-stu-id="95731-396">String</span></span>|  
|<span data-ttu-id="95731-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-397">COLLATION_NAME</span></span>|<span data-ttu-id="95731-398">String</span><span class="sxs-lookup"><span data-stu-id="95731-398">String</span></span>|  
|<span data-ttu-id="95731-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="95731-400">String</span><span class="sxs-lookup"><span data-stu-id="95731-400">String</span></span>|  
|<span data-ttu-id="95731-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="95731-402">String</span><span class="sxs-lookup"><span data-stu-id="95731-402">String</span></span>|  
|<span data-ttu-id="95731-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-403">DOMAIN_NAME</span></span>|<span data-ttu-id="95731-404">String</span><span class="sxs-lookup"><span data-stu-id="95731-404">String</span></span>|  
|<span data-ttu-id="95731-405">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-405">DESCRIPTION</span></span>|<span data-ttu-id="95731-406">String</span><span class="sxs-lookup"><span data-stu-id="95731-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="95731-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="95731-407">Procedures</span></span>  
  
|<span data-ttu-id="95731-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-408">ColumnName</span></span>|<span data-ttu-id="95731-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="95731-411">String</span><span class="sxs-lookup"><span data-stu-id="95731-411">String</span></span>|  
|<span data-ttu-id="95731-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="95731-413">String</span><span class="sxs-lookup"><span data-stu-id="95731-413">String</span></span>|  
|<span data-ttu-id="95731-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="95731-415">String</span><span class="sxs-lookup"><span data-stu-id="95731-415">String</span></span>|  
|<span data-ttu-id="95731-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="95731-417">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-417">Int16</span></span>|  
|<span data-ttu-id="95731-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="95731-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="95731-419">String</span><span class="sxs-lookup"><span data-stu-id="95731-419">String</span></span>|  
|<span data-ttu-id="95731-420">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-420">DESCRIPTION</span></span>|<span data-ttu-id="95731-421">String</span><span class="sxs-lookup"><span data-stu-id="95731-421">String</span></span>|  
|<span data-ttu-id="95731-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-422">DATE_CREATED</span></span>|<span data-ttu-id="95731-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-423">DateTime</span></span>|  
|<span data-ttu-id="95731-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-424">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="95731-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="95731-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="95731-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-427">ColumnName</span></span>|<span data-ttu-id="95731-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="95731-430">String</span><span class="sxs-lookup"><span data-stu-id="95731-430">String</span></span>|  
|<span data-ttu-id="95731-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="95731-432">String</span><span class="sxs-lookup"><span data-stu-id="95731-432">String</span></span>|  
|<span data-ttu-id="95731-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="95731-434">String</span><span class="sxs-lookup"><span data-stu-id="95731-434">String</span></span>|  
|<span data-ttu-id="95731-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-435">COLUMN_NAME</span></span>|<span data-ttu-id="95731-436">String</span><span class="sxs-lookup"><span data-stu-id="95731-436">String</span></span>|  
|<span data-ttu-id="95731-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-437">COLUMN_GUID</span></span>|<span data-ttu-id="95731-438">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-438">Guid</span></span>|  
|<span data-ttu-id="95731-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-439">COLUMN_PROPID</span></span>|<span data-ttu-id="95731-440">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-440">Int64</span></span>|  
|<span data-ttu-id="95731-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="95731-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="95731-442">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-442">Int64</span></span>|  
|<span data-ttu-id="95731-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-444">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-444">Int64</span></span>|  
|<span data-ttu-id="95731-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="95731-445">IS_NULLABLE</span></span>|<span data-ttu-id="95731-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-446">Boolean</span></span>|  
|<span data-ttu-id="95731-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-447">DATA_TYPE</span></span>|<span data-ttu-id="95731-448">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-448">Int32</span></span>|  
|<span data-ttu-id="95731-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-449">TYPE_GUID</span></span>|<span data-ttu-id="95731-450">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-450">Guid</span></span>|  
|<span data-ttu-id="95731-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="95731-452">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-452">Int64</span></span>|  
|<span data-ttu-id="95731-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="95731-454">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-454">Int64</span></span>|  
|<span data-ttu-id="95731-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="95731-456">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-456">Int32</span></span>|  
|<span data-ttu-id="95731-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="95731-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="95731-458">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-458">Int16</span></span>|  
|<span data-ttu-id="95731-459">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-459">DESCRIPTION</span></span>|<span data-ttu-id="95731-460">String</span><span class="sxs-lookup"><span data-stu-id="95731-460">String</span></span>|  
|<span data-ttu-id="95731-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="95731-461">OVERLOAD</span></span>|<span data-ttu-id="95731-462">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="95731-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="95731-463">Views</span></span>  
  
|<span data-ttu-id="95731-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-464">ColumnName</span></span>|<span data-ttu-id="95731-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-466">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-467">String</span><span class="sxs-lookup"><span data-stu-id="95731-467">String</span></span>|  
|<span data-ttu-id="95731-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-469">String</span><span class="sxs-lookup"><span data-stu-id="95731-469">String</span></span>|  
|<span data-ttu-id="95731-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-470">TABLE_NAME</span></span>|<span data-ttu-id="95731-471">String</span><span class="sxs-lookup"><span data-stu-id="95731-471">String</span></span>|  
|<span data-ttu-id="95731-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="95731-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="95731-473">String</span><span class="sxs-lookup"><span data-stu-id="95731-473">String</span></span>|  
|<span data-ttu-id="95731-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="95731-474">CHECK_OPTION</span></span>|<span data-ttu-id="95731-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-475">Boolean</span></span>|  
|<span data-ttu-id="95731-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="95731-476">IS_UPDATABLE</span></span>|<span data-ttu-id="95731-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-477">Boolean</span></span>|  
|<span data-ttu-id="95731-478">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-478">DESCRIPTION</span></span>|<span data-ttu-id="95731-479">String</span><span class="sxs-lookup"><span data-stu-id="95731-479">String</span></span>|  
|<span data-ttu-id="95731-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-480">DATE_CREATED</span></span>|<span data-ttu-id="95731-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-481">DateTime</span></span>|  
|<span data-ttu-id="95731-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-482">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="95731-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="95731-484">Indexes</span></span>  
  
|<span data-ttu-id="95731-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-485">ColumnName</span></span>|<span data-ttu-id="95731-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-487">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-488">String</span><span class="sxs-lookup"><span data-stu-id="95731-488">String</span></span>|  
|<span data-ttu-id="95731-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-490">String</span><span class="sxs-lookup"><span data-stu-id="95731-490">String</span></span>|  
|<span data-ttu-id="95731-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-491">TABLE_NAME</span></span>|<span data-ttu-id="95731-492">String</span><span class="sxs-lookup"><span data-stu-id="95731-492">String</span></span>|  
|<span data-ttu-id="95731-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-493">INDEX_CATALOG</span></span>|<span data-ttu-id="95731-494">String</span><span class="sxs-lookup"><span data-stu-id="95731-494">String</span></span>|  
|<span data-ttu-id="95731-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="95731-496">String</span><span class="sxs-lookup"><span data-stu-id="95731-496">String</span></span>|  
|<span data-ttu-id="95731-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-497">INDEX_NAME</span></span>|<span data-ttu-id="95731-498">String</span><span class="sxs-lookup"><span data-stu-id="95731-498">String</span></span>|  
|<span data-ttu-id="95731-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="95731-499">PRIMARY_KEY</span></span>|<span data-ttu-id="95731-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-500">Boolean</span></span>|  
|<span data-ttu-id="95731-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="95731-501">UNIQUE</span></span>|<span data-ttu-id="95731-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-502">Boolean</span></span>|  
|<span data-ttu-id="95731-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="95731-503">CLUSTERED</span></span>|<span data-ttu-id="95731-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-504">Boolean</span></span>|  
|<span data-ttu-id="95731-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-505">TYPE</span></span>|<span data-ttu-id="95731-506">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-506">Int32</span></span>|  
|<span data-ttu-id="95731-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="95731-507">FILL_FACTOR</span></span>|<span data-ttu-id="95731-508">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-508">Int32</span></span>|  
|<span data-ttu-id="95731-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="95731-509">INITIAL_SIZE</span></span>|<span data-ttu-id="95731-510">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-510">Int32</span></span>|  
|<span data-ttu-id="95731-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="95731-511">NULLS</span></span>|<span data-ttu-id="95731-512">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-512">Int32</span></span>|  
|<span data-ttu-id="95731-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="95731-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="95731-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-514">Boolean</span></span>|  
|<span data-ttu-id="95731-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="95731-515">AUTO_UPDATE</span></span>|<span data-ttu-id="95731-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-516">Boolean</span></span>|  
|<span data-ttu-id="95731-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="95731-517">NULL_COLLATION</span></span>|<span data-ttu-id="95731-518">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-518">Int32</span></span>|  
|<span data-ttu-id="95731-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-520">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-520">Int64</span></span>|  
|<span data-ttu-id="95731-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-521">COLUMN_NAME</span></span>|<span data-ttu-id="95731-522">String</span><span class="sxs-lookup"><span data-stu-id="95731-522">String</span></span>|  
|<span data-ttu-id="95731-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-523">COLUMN_GUID</span></span>|<span data-ttu-id="95731-524">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-524">Guid</span></span>|  
|<span data-ttu-id="95731-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-525">COLUMN_PROPID</span></span>|<span data-ttu-id="95731-526">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-526">Int64</span></span>|  
|<span data-ttu-id="95731-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="95731-527">COLLATION</span></span>|<span data-ttu-id="95731-528">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-528">Int16</span></span>|  
|<span data-ttu-id="95731-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="95731-529">CARDINALITY</span></span>|<span data-ttu-id="95731-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="95731-530">Decimal</span></span>|  
|<span data-ttu-id="95731-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="95731-531">PAGES</span></span>|<span data-ttu-id="95731-532">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-532">Int32</span></span>|  
|<span data-ttu-id="95731-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="95731-533">FILTER_CONDITION</span></span>|<span data-ttu-id="95731-534">String</span><span class="sxs-lookup"><span data-stu-id="95731-534">String</span></span>|  
|<span data-ttu-id="95731-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="95731-535">INTEGRATED</span></span>|<span data-ttu-id="95731-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="95731-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="95731-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="95731-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="95731-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="95731-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="95731-539">Tables</span></span>  
  
- <span data-ttu-id="95731-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="95731-540">Columns</span></span>  
  
- <span data-ttu-id="95731-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="95731-541">Procedures</span></span>  
  
- <span data-ttu-id="95731-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="95731-542">Views</span></span>  
  
- <span data-ttu-id="95731-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="95731-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="95731-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="95731-544">Tables</span></span>  
  
|<span data-ttu-id="95731-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-545">ColumnName</span></span>|<span data-ttu-id="95731-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-547">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-548">String</span><span class="sxs-lookup"><span data-stu-id="95731-548">String</span></span>|  
|<span data-ttu-id="95731-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-550">String</span><span class="sxs-lookup"><span data-stu-id="95731-550">String</span></span>|  
|<span data-ttu-id="95731-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-551">TABLE_NAME</span></span>|<span data-ttu-id="95731-552">String</span><span class="sxs-lookup"><span data-stu-id="95731-552">String</span></span>|  
|<span data-ttu-id="95731-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-553">TABLE_TYPE</span></span>|<span data-ttu-id="95731-554">String</span><span class="sxs-lookup"><span data-stu-id="95731-554">String</span></span>|  
|<span data-ttu-id="95731-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-555">TABLE_GUID</span></span>|<span data-ttu-id="95731-556">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-556">Guid</span></span>|  
|<span data-ttu-id="95731-557">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-557">DESCRIPTION</span></span>|<span data-ttu-id="95731-558">String</span><span class="sxs-lookup"><span data-stu-id="95731-558">String</span></span>|  
|<span data-ttu-id="95731-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-559">TABLE_PROPID</span></span>|<span data-ttu-id="95731-560">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-560">Int64</span></span>|  
|<span data-ttu-id="95731-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-561">DATE_CREATED</span></span>|<span data-ttu-id="95731-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-562">DateTime</span></span>|  
|<span data-ttu-id="95731-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-563">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="95731-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="95731-565">Columns</span></span>  
  
|<span data-ttu-id="95731-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-566">ColumnName</span></span>|<span data-ttu-id="95731-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-568">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-569">String</span><span class="sxs-lookup"><span data-stu-id="95731-569">String</span></span>|  
|<span data-ttu-id="95731-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-571">String</span><span class="sxs-lookup"><span data-stu-id="95731-571">String</span></span>|  
|<span data-ttu-id="95731-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-572">TABLE_NAME</span></span>|<span data-ttu-id="95731-573">String</span><span class="sxs-lookup"><span data-stu-id="95731-573">String</span></span>|  
|<span data-ttu-id="95731-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-574">COLUMN_NAME</span></span>|<span data-ttu-id="95731-575">String</span><span class="sxs-lookup"><span data-stu-id="95731-575">String</span></span>|  
|<span data-ttu-id="95731-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-576">COLUMN_GUID</span></span>|<span data-ttu-id="95731-577">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-577">Guid</span></span>|  
|<span data-ttu-id="95731-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-578">COLUMN_PROPID</span></span>|<span data-ttu-id="95731-579">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-579">Int64</span></span>|  
|<span data-ttu-id="95731-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-581">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-581">Int64</span></span>|  
|<span data-ttu-id="95731-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="95731-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-583">Boolean</span></span>|  
|<span data-ttu-id="95731-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="95731-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="95731-585">String</span><span class="sxs-lookup"><span data-stu-id="95731-585">String</span></span>|  
|<span data-ttu-id="95731-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="95731-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="95731-587">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-587">Int64</span></span>|  
|<span data-ttu-id="95731-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="95731-588">IS_NULLABLE</span></span>|<span data-ttu-id="95731-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-589">Boolean</span></span>|  
|<span data-ttu-id="95731-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-590">DATA_TYPE</span></span>|<span data-ttu-id="95731-591">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-591">Int32</span></span>|  
|<span data-ttu-id="95731-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-592">TYPE_GUID</span></span>|<span data-ttu-id="95731-593">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-593">Guid</span></span>|  
|<span data-ttu-id="95731-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="95731-595">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-595">Int64</span></span>|  
|<span data-ttu-id="95731-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="95731-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="95731-597">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-597">Int64</span></span>|  
|<span data-ttu-id="95731-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="95731-599">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-599">Int32</span></span>|  
|<span data-ttu-id="95731-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="95731-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="95731-601">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-601">Int16</span></span>|  
|<span data-ttu-id="95731-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="95731-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="95731-603">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-603">Int64</span></span>|  
|<span data-ttu-id="95731-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="95731-605">String</span><span class="sxs-lookup"><span data-stu-id="95731-605">String</span></span>|  
|<span data-ttu-id="95731-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="95731-607">String</span><span class="sxs-lookup"><span data-stu-id="95731-607">String</span></span>|  
|<span data-ttu-id="95731-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="95731-609">String</span><span class="sxs-lookup"><span data-stu-id="95731-609">String</span></span>|  
|<span data-ttu-id="95731-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="95731-611">String</span><span class="sxs-lookup"><span data-stu-id="95731-611">String</span></span>|  
|<span data-ttu-id="95731-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="95731-613">String</span><span class="sxs-lookup"><span data-stu-id="95731-613">String</span></span>|  
|<span data-ttu-id="95731-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-614">COLLATION_NAME</span></span>|<span data-ttu-id="95731-615">String</span><span class="sxs-lookup"><span data-stu-id="95731-615">String</span></span>|  
|<span data-ttu-id="95731-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="95731-617">String</span><span class="sxs-lookup"><span data-stu-id="95731-617">String</span></span>|  
|<span data-ttu-id="95731-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="95731-619">String</span><span class="sxs-lookup"><span data-stu-id="95731-619">String</span></span>|  
|<span data-ttu-id="95731-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-620">DOMAIN_NAME</span></span>|<span data-ttu-id="95731-621">String</span><span class="sxs-lookup"><span data-stu-id="95731-621">String</span></span>|  
|<span data-ttu-id="95731-622">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-622">DESCRIPTION</span></span>|<span data-ttu-id="95731-623">String</span><span class="sxs-lookup"><span data-stu-id="95731-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="95731-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="95731-624">Procedures</span></span>  
  
|<span data-ttu-id="95731-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-625">ColumnName</span></span>|<span data-ttu-id="95731-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="95731-628">String</span><span class="sxs-lookup"><span data-stu-id="95731-628">String</span></span>|  
|<span data-ttu-id="95731-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="95731-630">String</span><span class="sxs-lookup"><span data-stu-id="95731-630">String</span></span>|  
|<span data-ttu-id="95731-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="95731-632">String</span><span class="sxs-lookup"><span data-stu-id="95731-632">String</span></span>|  
|<span data-ttu-id="95731-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="95731-634">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-634">Int16</span></span>|  
|<span data-ttu-id="95731-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="95731-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="95731-636">String</span><span class="sxs-lookup"><span data-stu-id="95731-636">String</span></span>|  
|<span data-ttu-id="95731-637">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-637">DESCRIPTION</span></span>|<span data-ttu-id="95731-638">String</span><span class="sxs-lookup"><span data-stu-id="95731-638">String</span></span>|  
|<span data-ttu-id="95731-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-639">DATE_CREATED</span></span>|<span data-ttu-id="95731-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-640">DateTime</span></span>|  
|<span data-ttu-id="95731-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-641">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="95731-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="95731-643">Views</span></span>  
  
|<span data-ttu-id="95731-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-644">ColumnName</span></span>|<span data-ttu-id="95731-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-646">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-647">String</span><span class="sxs-lookup"><span data-stu-id="95731-647">String</span></span>|  
|<span data-ttu-id="95731-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-649">String</span><span class="sxs-lookup"><span data-stu-id="95731-649">String</span></span>|  
|<span data-ttu-id="95731-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-650">TABLE_NAME</span></span>|<span data-ttu-id="95731-651">String</span><span class="sxs-lookup"><span data-stu-id="95731-651">String</span></span>|  
|<span data-ttu-id="95731-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="95731-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="95731-653">String</span><span class="sxs-lookup"><span data-stu-id="95731-653">String</span></span>|  
|<span data-ttu-id="95731-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="95731-654">CHECK_OPTION</span></span>|<span data-ttu-id="95731-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-655">Boolean</span></span>|  
|<span data-ttu-id="95731-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="95731-656">IS_UPDATABLE</span></span>|<span data-ttu-id="95731-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-657">Boolean</span></span>|  
|<span data-ttu-id="95731-658">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95731-658">DESCRIPTION</span></span>|<span data-ttu-id="95731-659">String</span><span class="sxs-lookup"><span data-stu-id="95731-659">String</span></span>|  
|<span data-ttu-id="95731-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="95731-660">DATE_CREATED</span></span>|<span data-ttu-id="95731-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-661">DateTime</span></span>|  
|<span data-ttu-id="95731-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="95731-662">DATE_MODIFIED</span></span>|<span data-ttu-id="95731-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="95731-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="95731-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="95731-664">Indexes</span></span>  
  
|<span data-ttu-id="95731-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="95731-665">ColumnName</span></span>|<span data-ttu-id="95731-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95731-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="95731-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-667">TABLE_CATALOG</span></span>|<span data-ttu-id="95731-668">String</span><span class="sxs-lookup"><span data-stu-id="95731-668">String</span></span>|  
|<span data-ttu-id="95731-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="95731-670">String</span><span class="sxs-lookup"><span data-stu-id="95731-670">String</span></span>|  
|<span data-ttu-id="95731-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-671">TABLE_NAME</span></span>|<span data-ttu-id="95731-672">String</span><span class="sxs-lookup"><span data-stu-id="95731-672">String</span></span>|  
|<span data-ttu-id="95731-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="95731-673">INDEX_CATALOG</span></span>|<span data-ttu-id="95731-674">String</span><span class="sxs-lookup"><span data-stu-id="95731-674">String</span></span>|  
|<span data-ttu-id="95731-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="95731-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="95731-676">String</span><span class="sxs-lookup"><span data-stu-id="95731-676">String</span></span>|  
|<span data-ttu-id="95731-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-677">INDEX_NAME</span></span>|<span data-ttu-id="95731-678">String</span><span class="sxs-lookup"><span data-stu-id="95731-678">String</span></span>|  
|<span data-ttu-id="95731-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="95731-679">PRIMARY_KEY</span></span>|<span data-ttu-id="95731-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-680">Boolean</span></span>|  
|<span data-ttu-id="95731-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="95731-681">UNIQUE</span></span>|<span data-ttu-id="95731-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-682">Boolean</span></span>|  
|<span data-ttu-id="95731-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="95731-683">CLUSTERED</span></span>|<span data-ttu-id="95731-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-684">Boolean</span></span>|  
|<span data-ttu-id="95731-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="95731-685">TYPE</span></span>|<span data-ttu-id="95731-686">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-686">Int32</span></span>|  
|<span data-ttu-id="95731-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="95731-687">FILL_FACTOR</span></span>|<span data-ttu-id="95731-688">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-688">Int32</span></span>|  
|<span data-ttu-id="95731-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="95731-689">INITIAL_SIZE</span></span>|<span data-ttu-id="95731-690">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-690">Int32</span></span>|  
|<span data-ttu-id="95731-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="95731-691">NULLS</span></span>|<span data-ttu-id="95731-692">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-692">Int32</span></span>|  
|<span data-ttu-id="95731-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="95731-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="95731-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-694">Boolean</span></span>|  
|<span data-ttu-id="95731-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="95731-695">AUTO_UPDATE</span></span>|<span data-ttu-id="95731-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-696">Boolean</span></span>|  
|<span data-ttu-id="95731-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="95731-697">NULL_COLLATION</span></span>|<span data-ttu-id="95731-698">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-698">Int32</span></span>|  
|<span data-ttu-id="95731-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="95731-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="95731-700">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-700">Int64</span></span>|  
|<span data-ttu-id="95731-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="95731-701">COLUMN_NAME</span></span>|<span data-ttu-id="95731-702">String</span><span class="sxs-lookup"><span data-stu-id="95731-702">String</span></span>|  
|<span data-ttu-id="95731-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="95731-703">COLUMN_GUID</span></span>|<span data-ttu-id="95731-704">Guid</span><span class="sxs-lookup"><span data-stu-id="95731-704">Guid</span></span>|  
|<span data-ttu-id="95731-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="95731-705">COLUMN_PROPID</span></span>|<span data-ttu-id="95731-706">Int64</span><span class="sxs-lookup"><span data-stu-id="95731-706">Int64</span></span>|  
|<span data-ttu-id="95731-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="95731-707">COLLATION</span></span>|<span data-ttu-id="95731-708">Int16</span><span class="sxs-lookup"><span data-stu-id="95731-708">Int16</span></span>|  
|<span data-ttu-id="95731-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="95731-709">CARDINALITY</span></span>|<span data-ttu-id="95731-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="95731-710">Decimal</span></span>|  
|<span data-ttu-id="95731-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="95731-711">PAGES</span></span>|<span data-ttu-id="95731-712">Int32</span><span class="sxs-lookup"><span data-stu-id="95731-712">Int32</span></span>|  
|<span data-ttu-id="95731-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="95731-713">FILTER_CONDITION</span></span>|<span data-ttu-id="95731-714">String</span><span class="sxs-lookup"><span data-stu-id="95731-714">String</span></span>|  
|<span data-ttu-id="95731-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="95731-715">INTEGRATED</span></span>|<span data-ttu-id="95731-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="95731-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95731-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95731-717">See also</span></span>

- [<span data-ttu-id="95731-718">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95731-718">ADO.NET Overview</span></span>](ado-net-overview.md)
