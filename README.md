# RTM-Tool-Base-Open-Source
A simple RTM Tool open source with function for toggle ON / OFF easy. If you want to create a RTM Tool on PS3 you can use this source made by me.

For add your mods, go in the class Functions and create a simple void like this:

 public void NAME_MODS(bool toggle)
        {
            try
            {
                if (this.PS3.AttachProcess() && toggle)
                {
                    PS3.SetMemory(0x000000, new byte[] { 0x80 });
                }
                else if (!toggle)
                {
                    PS3.SetMemory(0x000000, new byte[] { 0x20 });
                }
            }
            catch (Exception)
            {
                MessageBox.Show("Base RTM, need to be connected or attached to the PS3 !", "Base RTM", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }
        
change the offset (0x000000) to your offset with the good values and if you want add this for enable / disable it on a check box make this:

FUNCTIONS.NAME_MODS(true); //for enable it
FUNCTIONS.NAME_MODS(false); //for disable it
