 JMenuBar jmb=new JMenuBar(); 
JMenu jmFile=new JMenu("文件");  
JMenuItem jmiNew=new JMenuItem("新建"); 
JMenuItem jmiOpen=new JMenuItem("打开"); 
jmiOpen.addActionListener(this);  
 jmFile.add(jmiNew); 
jmFile.add(jmiOpen); 
JMenu jmFenxi=new JMenu("分析");  
JMenuItem jmiQue=new JMenuItem("确定"); 
JMenuItem jmiQu=new JMenuItem("取消"); 
jmFenxi.add(jmiQue); 
jmFenxi.add(jmiQu); 
jmiQue.addActionListener(new ActionListener() 
public void actionPerformed(ActionEvent e) 
{   String filterText = jta.getText(); 
try 
{  
jta.setText(Fenx.getFilterText(filterText)); 
}
 catch(Exception exx) 
{ exx.printStackTrace(); 
}  
}  
});  
JMenu jmHelp=new JMenu("帮助"); 
jmb.add(jmFile); 
jmb.add(jmFenxi); 
jmb.add(jmHelp);  
this.setJMenuBar(jmb);  
this.getContentPane().add(jta); 
 this.setVisible(true); 
public void actionPerformed(ActionEvent e) 
{  
JFileChooser jc=new JFileChooser(); 
jc.showOpenDialog(this); 
try 
{  
File file=jc.getSelectedFile();  
FileInputStream fis=new FileInputStream(file); 
byte[] buf=new byte[10*1024]; 
int len=fis.read(buf);  
jta.append(new String(buf,0,len)); 
}  
catch(Exception ex) 
{  
ex.printStackTrace(); 
} 
}  
 public static void main(String[] args) 
{  
TestJMenu jmFrame=new TestJMenu();  
jmFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); 
} 
} 
