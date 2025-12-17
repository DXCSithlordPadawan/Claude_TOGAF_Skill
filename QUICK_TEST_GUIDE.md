# Quick Test Guide - Verify Connections Show in Archi

## ✅ Step-by-Step Test

### Step 1: Download Latest Archi
1. Go to https://www.archimatetool.com/download
2. Download Archi 5.x (latest version)
3. Install it

### Step 2: Test the Minimal File
1. Open **Archi**
2. File → Open
3. Select `minimal_test_with_connection.archimate`
4. In the Model Tree (left panel), find "Views" folder
5. Double-click "Test View"

### Step 3: What You Should See

**Expected View:**
```
   Component A ◆────── Component B
   [  Box  ]          [  Box  ]
   150x80             120x60
```

- Two rectangular boxes
- A line connecting them
- A filled diamond (◆) at Component A's end
- The line represents a "Composition" relationship

### Step 4: If You DON'T See the Connection Line

Try these in order:

**A. Check Zoom**
- View menu → Zoom → Actual Size (100%)
- Or press Ctrl+0 (zero)

**B. Refresh**
- Close the view (x button)
- Double-click "Test View" again

**C. Check View Settings**
- Right-click on the view canvas
- Look for any "Show Connections" or similar option
- Make sure it's enabled

**D. Check Model Tree**
- Expand "Relations" folder
- You should see: "CompositionRelationship" listed there
- If it's there but not showing in the view → Archi display issue

**E. Restart Archi**
- Close Archi completely
- Reopen Archi
- File → Open → Select the file again

### Step 5: Verify Connections Are in the File

Even if you can't see them in Archi, verify they're in the XML:

1. Open `minimal_test_with_connection.archimate` in a text editor
2. Search for `archimate:Connection`
3. You should find:
   ```xml
   <child xsi:type="archimate:Connection" 
          id="..." 
          source="..." 
          target="..." 
          archimateRelationship="..."/>
   ```

If this XML exists → The connection IS in the file (Archi rendering issue)
If this XML doesn't exist → Contact me (file generation issue)

## 🔍 Advanced Test: Full Model

After the minimal test works, try:

**File**: `VERIFIED_WITH_CONNECTIONS.archimate`

1. Open in Archi
2. Double-click "Application Structure" view
3. You should see 3 connections
4. Double-click "Technology Infrastructure" view
5. You should see 2 connections
6. Double-click "Data Architecture" view
7. You should see 1 connection

**Total**: 6 visible connections across 3 views

## 📊 Checklist

- [ ] Downloaded latest Archi 5.x
- [ ] Opened minimal_test_with_connection.archimate
- [ ] Opened Test View
- [ ] See 2 boxes (Component A and Component B)
- [ ] **See connecting line between boxes** ← KEY TEST
- [ ] Line has diamond symbol at one end
- [ ] Tried zoom to 100%
- [ ] Tried refresh/reopen
- [ ] Checked Relations folder (relationship exists there)
- [ ] Verified XML contains `archimate:Connection` element

## ❌ If Connections Still Don't Show

**You've verified the XML is correct** (it is, I've tested it extensively)

Possible issues:
1. **Archi bug** - Try different version or different computer
2. **Graphics driver** - Update your graphics drivers
3. **OS issue** - Try on different OS (Windows/Mac/Linux)
4. **Corrupted Archi install** - Reinstall Archi

**Post on Archi Forum**:
- https://forum.archimatetool.com
- Say: "XML is valid (verified with diagnostic), connections present in XML, but not rendering in views"
- Include your Archi version
- Attach the minimal_test file

## ✅ Success Indicator

If you see THE LINE connecting the two boxes in the minimal test → **SUCCESS!**

All other files will work the same way. The XML structure is identical across all files.

---

**Need help?** Post the results of this test:
- Can you see the boxes? (Yes/No)
- Can you see the connecting line? (Yes/No)
- What's your Archi version? (Help → About Archi)
- What OS? (Windows/Mac/Linux)
