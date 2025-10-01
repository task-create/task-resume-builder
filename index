<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TASK Resume Builder</title>
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Arial, sans-serif; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); padding: 20px; min-height: 100vh; }
.container { max-width: 800px; margin: 0 auto; background: white; border-radius: 20px; box-shadow: 0 20px 60px rgba(0,0,0,0.3); overflow: hidden; }
.header { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 40px 30px; text-align: center; }
.header h1 { font-size: 36px; margin-bottom: 10px; }
.header p { font-size: 18px; opacity: 0.95; }
.progress-bar { background: rgba(255,255,255,0.2); height: 6px; border-radius: 3px; margin-top: 20px; overflow: hidden; }
.progress-fill { background: white; height: 100%; width: 0%; transition: width 0.3s ease; }
.form-content { padding: 40px 30px; }
.section { margin-bottom: 40px; display: none; }
.section.active { display: block; animation: fadeIn 0.5s ease; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
.section-header { display: flex; align-items: center; margin-bottom: 20px; padding-bottom: 15px; border-bottom: 3px solid #667eea; }
.section-icon { font-size: 32px; margin-right: 15px; }
.section-title { flex: 1; }
.section-title h2 { font-size: 24px; color: #333; margin-bottom: 5px; }
.section-title p { font-size: 14px; color: #666; }
.form-group { margin-bottom: 25px; }
label { display: block; font-weight: 600; color: #333; margin-bottom: 8px; font-size: 15px; }
.label-help { font-weight: 400; color: #666; font-size: 13px; margin-left: 5px; }
input[type="text"], input[type="email"], input[type="tel"], textarea, select { width: 100%; padding: 12px 15px; border: 2px solid #e0e0e0; border-radius: 10px; font-size: 15px; font-family: inherit; transition: border-color 0.3s ease; }
input:focus, textarea:focus, select:focus { outline: none; border-color: #667eea; }
textarea { min-height: 120px; resize: vertical; }
.example-box { background: #f8f9ff; border-left: 4px solid #667eea; padding: 15px; margin-top: 10px; border-radius: 8px; }
.example-box strong { color: #667eea; display: block; margin-bottom: 8px; font-size: 14px; }
.example-box p { color: #555; font-size: 13px; line-height: 1.6; margin: 5px 0; }
.tip-box { background: #fff7e6; border-left: 4px solid #ffa726; padding: 15px; margin: 20px 0; border-radius: 8px; }
.tip-box strong { color: #f57c00; display: block; margin-bottom: 8px; font-size: 14px; }
.tip-box ul { margin-left: 20px; color: #666; font-size: 13px; line-height: 1.8; }
.button-group { display: flex; gap: 15px; margin-top: 30px; }
button { flex: 1; padding: 15px 30px; border: none; border-radius: 10px; font-size: 16px; font-weight: 600; cursor: pointer; transition: all 0.3s ease; }
.btn-primary { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4); }
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(102, 126, 234, 0.6); }
.btn-secondary { background: white; color: #667eea; border: 2px solid #667eea; }
.btn-secondary:hover { background: #f8f9ff; }
.btn-success { background: #10b981; color: white; box-shadow: 0 4px 15px rgba(16, 185, 129, 0.4); }
.btn-success:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(16, 185, 129, 0.6); }
.add-more { display: inline-block; color: #667eea; font-size: 14px; font-weight: 600; cursor: pointer; margin-top: 10px; text-decoration: underline; }
.add-more:hover { color: #764ba2; }
.entry-group { background: #f9f9f9; padding: 20px; border-radius: 10px; margin-bottom: 20px; position: relative; }
.remove-entry { position: absolute; top: 15px; right: 15px; background: #ef4444; color: white; border: none; width: 30px; height: 30px; border-radius: 50%; cursor: pointer; font-size: 18px; line-height: 1; }
.step-indicator { text-align: center; color: #667eea; font-weight: 600; margin-bottom: 10px; font-size: 14px; }
#preview { background: white; padding: 40px; border: 1px solid #e0e0e0; border-radius: 10px; font-family: 'Times New Roman', serif; max-width: 700px; margin: 0 auto; }
#preview h3 { color: #333; font-size: 28px; margin-bottom: 5px; text-align: center; }
#preview .contact-info { text-align: center; color: #666; font-size: 14px; margin-bottom: 20px; padding-bottom: 15px; border-bottom: 2px solid #333; }
#preview h4 { color: #333; font-size: 18px; margin-top: 20px; margin-bottom: 10px; text-transform: uppercase; border-bottom: 1px solid #333; padding-bottom: 5px; }
#preview .job-entry, #preview .edu-entry { margin-bottom: 15px; }
#preview .job-title { font-weight: bold; color: #333; }
#preview .company { font-style: italic; color: #555; }
#preview ul { margin-left: 20px; margin-top: 5px; }
#preview li { margin-bottom: 5px; color: #444; line-height: 1.6; }
.download-buttons { display: flex; gap: 15px; margin-top: 20px; }
@media (max-width: 768px) { .container { border-radius: 0; } .header h1 { font-size: 28px; } .form-content { padding: 30px 20px; } .button-group { flex-direction: column; } #preview { padding: 20px; } }
</style>
</head>
<body>
<div class="container">
<div class="header">
<h1>💼 TASK Resume Builder</h1>
<p>Build your professional resume step-by-step</p>
<div class="progress-bar"><div class="progress-fill" id="progressBar"></div></div>
</div>
<div class="form-content">
<form id="resumeForm">
<div class="section active" data-section="1">
<div class="step-indicator">Step 1 of 5</div>
<div class="section-header">
<div class="section-icon">👤</div>
<div class="section-title"><h2>Personal Information</h2><p>Let's start with your contact details</p></div>
</div>
<div class="form-group"><label>Full Name *</label><input type="text" id="fullName" required placeholder="John Smith"></div>
<div class="form-group"><label>Phone Number *</label><input type="tel" id="phone" required placeholder="(609) 555-1234"></div>
<div class="form-group"><label>Email Address *</label><input type="email" id="email" required placeholder="john.smith@email.com"></div>
<div class="form-group"><label>City, State</label><input type="text" id="location" placeholder="Trenton, NJ"></div>
<div class="button-group"><button type="button" class="btn-primary" id="nextBtn1">Next Step →</button></div>
</div>
<div class="section" data-section="2">
<div class="step-indicator">Step 2 of 5</div>
<div class="section-header">
<div class="section-icon">💼</div>
<div class="section-title"><h2>Work Experience</h2><p>Tell us about your jobs using the C·A·R method</p></div>
</div>
<div class="tip-box"><strong>💡 C·A·R Method Tips:</strong><ul><li><strong>Challenge:</strong> What problem did you face?</li><li><strong>Action:</strong> What did you do about it?</li><li><strong>Result:</strong> What improved? (Use numbers!)</li></ul></div>
<div id="workExperiences">
<div class="entry-group">
<div class="form-group"><label>Job Title *</label><input type="text" name="jobTitle[]" required placeholder="Warehouse Associate"></div>
<div class="form-group"><label>Company Name *</label><input type="text" name="company[]" required placeholder="ABC Logistics"></div>
<div class="form-group"><label>Dates Worked <span class="label-help">(Month Year - Month Year)</span></label><input type="text" name="dates[]" placeholder="January 2020 - Present"></div>
<div class="form-group"><label>What did you do? Use C·A·R method *</label><textarea name="responsibilities[]" required placeholder="Example:&#10;• Challenge: Pick errors were high (15% error rate)&#10;• Action: Reorganized bin layout and trained 5 team members&#10;• Result: Reduced errors to 5% and improved pick speed by 25%"></textarea>
<div class="example-box"><strong>✅ Good Example:</strong><p>• Challenge: Shipping delays were causing customer complaints</p><p>• Action: Created new packing checklist and trained team</p><p>• Result: Cut shipping errors by 40% and improved ratings from 3.5 to 4.8 stars</p></div>
</div>
</div>
</div>
<span class="add-more" id="addWork">+ Add Another Job</span>
<div class="button-group"><button type="button" class="btn-secondary" id="prevBtn2">← Back</button><button type="button" class="btn-primary" id="nextBtn2">Next Step →</button></div>
</div>
<div class="section" data-section="3">
<div class="step-indicator">Step 3 of 5</div>
<div class="section-header">
<div class="section-icon">🎓</div>
<div class="section-title"><h2>Education</h2><p>List your education and training</p></div>
</div>
<div id="educationEntries">
<div class="entry-group">
<div class="form-group"><label>Degree or Certificate *</label><input type="text" name="degree[]" required placeholder="High School Diploma"></div>
<div class="form-group"><label>School Name *</label><input type="text" name="school[]" required placeholder="Trenton Central High School"></div>
<div class="form-group"><label>Year Graduated</label><input type="text" name="gradYear[]" placeholder="2018"></div>
</div>
</div>
<span class="add-more" id="addEdu">+ Add More Education</span>
<div class="tip-box"><strong>💡 Don't have formal education?</strong><ul><li>List any training programs, certifications, or courses</li><li>Include GED if you have one</li><li>Add relevant online courses or workshops</li></ul></div>
<div class="button-group"><button type="button" class="btn-secondary" id="prevBtn3">← Back</button><button type="button" class="btn-primary" id="nextBtn3">Next Step →</button></div>
</div>
<div class="section" data-section="4">
<div class="step-indicator">Step 4 of 5</div>
<div class="section-header">
<div class="section-icon">⭐</div>
<div class="section-title"><h2>Skills</h2><p>What are you good at?</p></div>
</div>
<div class="form-group"><label>Your Skills <span class="label-help">(List each skill separated by a comma)</span></label><textarea id="skills" placeholder="Example: Forklift certified, Customer service, Microsoft Office, Bilingual (English/Spanish), Team leadership, Time management"></textarea>
<div class="example-box"><strong>💡 Skill Ideas:</strong><p><strong>Technical:</strong> Forklift, Computer skills, Cash register, Equipment operation</p><p><strong>Soft Skills:</strong> Customer service, Teamwork, Problem solving, Communication</p><p><strong>Certifications:</strong> OSHA certified, Food handler's license, CDL</p><p><strong>Languages:</strong> Bilingual, Multilingual</p></div>
</div>
<div class="button-group"><button type="button" class="btn-secondary" id="prevBtn4">← Back</button><button type="button" class="btn-primary" id="nextBtn4">Next Step →</button></div>
</div>
<div class="section" data-section="5">
<div class="step-indicator">Step 5 of 5</div>
<div class="section-header">
<div class="section-icon">📄</div>
<div class="section-title"><h2>Review Your Resume</h2><p>Check everything looks good, then download or email</p></div>
</div>
<div id="preview"></div>
<div class="download-buttons">
<button type="button" class="btn-success" id="downloadBtn">📥 Download as PDF</button>
<button type="button" class="btn-primary" id="emailBtn">📧 Email to TASK</button>
</div>
<div class="button-group" style="margin-top: 20px;"><button type="button" class="btn-secondary" id="prevBtn5">← Edit Resume</button></div>
</div>
</form>
</div>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script>
let currentSection=1;const totalSections=5;function updateProgress(){document.getElementById('progressBar').style.width=(currentSection/totalSections)*100+'%'}function goToSection(n){document.querySelector(`.section[data-section="${currentSection}"]`).classList.remove('active');currentSection=n;document.querySelector(`.section[data-section="${currentSection}"]`).classList.add('active');updateProgress();window.scrollTo({top:0,behavior:'smooth'});if(currentSection===5)generatePreview()}function validateSection(n){const s=document.querySelector(`.section[data-section="${n}"]`),r=s.querySelectorAll('[required]');let v=true;if(n===1){r.forEach(f=>{if(!f.value.trim()){v=false;f.style.borderColor='#ef4444'}else{f.style.borderColor='#e0e0e0'}})}else{r.forEach(f=>{f.style.borderColor='#e0e0e0'})}if(!v)alert('Please fill in all required fields (marked with *)');return v}
document.getElementById('nextBtn1').addEventListener('click',()=>{if(validateSection(1))goToSection(2)});document.getElementById('nextBtn2').addEventListener('click',()=>{goToSection(3)});document.getElementById('prevBtn2').addEventListener('click',()=>{goToSection(1)});document.getElementById('nextBtn3').addEventListener('click',()=>{goToSection(4)});document.getElementById('prevBtn3').addEventListener('click',()=>{goToSection(2)});document.getElementById('nextBtn4').addEventListener('click',()=>{goToSection(5)});document.getElementById('prevBtn4').addEventListener('click',()=>{goToSection(3)});document.getElementById('prevBtn5').addEventListener('click',()=>{goToSection(4)});
document.getElementById('addWork').addEventListener('click',()=>{const c=document.getElementById('workExperiences'),n=document.createElement('div');n.className='entry-group';n.innerHTML='<button type="button" class="remove-entry">×</button><div class="form-group"><label>Job Title *</label><input type="text" name="jobTitle[]" required placeholder="Warehouse Associate"></div><div class="form-group"><label>Company Name *</label><input type="text" name="company[]" required placeholder="ABC Logistics"></div><div class="form-group"><label>Dates Worked</label><input type="text" name="dates[]" placeholder="January 2020 - Present"></div><div class="form-group"><label>What did you do? Use C·A·R method *</label><textarea name="responsibilities[]" required placeholder="List your accomplishments"></textarea></div>';c.appendChild(n);n.querySelector('.remove-entry').addEventListener('click',function(){n.remove()})});
document.getElementById('addEdu').addEventListener('click',()=>{const c=document.getElementById('educationEntries'),n=document.createElement('div');n.className='entry-group';n.innerHTML='<button type="button" class="remove-entry">×</button><div class="form-group"><label>Degree or Certificate *</label><input type="text" name="degree[]" required placeholder="High School Diploma"></div><div class="form-group"><label>School Name *</label><input type="text" name="school[]" required placeholder="School Name"></div><div class="form-group"><label>Year Graduated</label><input type="text" name="gradYear[]" placeholder="2018"></div>';c.appendChild(n);n.querySelector('.remove-entry').addEventListener('click',function(){n.remove()})});
function generatePreview(){const p=document.getElementById('preview'),n=document.getElementById('fullName').value,ph=document.getElementById('phone').value,e=document.getElementById('email').value,l=document.getElementById('location').value;let h=`<h3>${n}</h3><div class="contact-info">${l} | ${ph} | ${e}</div>`;const jt=document.getElementsByName('jobTitle[]'),c=document.getElementsByName('company[]'),d=document.getElementsByName('dates[]'),r=document.getElementsByName('responsibilities[]');if(jt.length>0&&jt[0].value){h+='<h4>Work Experience</h4>';for(let i=0;i<jt.length;i++){if(jt[i].value){h+=`<div class="job-entry"><div class="job-title">${jt[i].value}</div><div class="company">${c[i].value} | ${d[i].value||'Present'}</div><ul>`;const b=r[i].value.split('\n').filter(x=>x.trim());b.forEach(x=>{h+=`<li>${x.replace(/^[•\-*]\s*/,'')}</li>`});h+='</ul></div>'}}}const dg=document.getElementsByName('degree[]'),sc=document.getElementsByName('school[]'),gy=document.getElementsByName('gradYear[]');if(dg.length>0&&dg[0].value){h+='<h4>Education</h4>';for(let i=0;i<dg.length;i++){if(dg[i].value){h+=`<div class="edu-entry"><strong>${dg[i].value}</strong><br>${sc[i].value}${gy[i].value?', '+gy[i].value:''}</div>`}}}const sk=document.getElementById('skills').value;if(sk){h+='<h4>Skills</h4><p>'+sk+'</p>'}p.innerHTML=h}
document.getElementById('downloadBtn').addEventListener('click',()=>{const{jsPDF}=window.jspdf,doc=new jsPDF(),n=document.getElementById('fullName').value,ph=document.getElementById('phone').value,e=document.getElementById('email').value,l=document.getElementById('location').value;let y=20;doc.setFontSize(22);doc.setFont(undefined,'bold');doc.text(n,105,y,{align:'center'});y+=8;doc.setFontSize(10);doc.setFont(undefined,'normal');doc.text(`${l} | ${ph} | ${e}`,105,y,{align:'center'});y+=10;doc.setLineWidth(0.5);doc.line(20,y,190,y);y+=8;const jt=document.getElementsByName('jobTitle[]'),c=document.getElementsByName('company[]'),d=document.getElementsByName('dates[]'),r=document.getElementsByName('responsibilities[]');if(jt.length>0&&jt[0].value){doc.setFontSize(14);doc.setFont(undefined,'bold');doc.text('WORK EXPERIENCE',20,y);y+=7;for(let i=0;i<jt.length;i++){if(jt[i].value){doc.setFontSize(11);doc.setFont(undefined,'bold');doc.text(jt[i].value,20,y);y+=5;doc.setFont(undefined,'italic');doc.text(`${c[i].value} | ${d[i].value||'Present'}`,20,y);y+=6;doc.setFont(undefined,'normal');doc.setFontSize(10);const b=r[i].value.split('\n').filter(x=>x.trim());b.forEach(x=>{const l=doc.splitTextToSize('• '+x.replace(/^[•\-*]\s*/,''),170);l.forEach(ln=>{if(y>270){doc.addPage();y=20}doc.text(ln,20,y);y+=5})});y+=3}}}const dg=document.getElementsByName('degree[]'),sc=document.getElementsByName('school[]'),gy=document.getElementsByName('gradYear[]');if(dg.length>0&&dg[0].value){if(y>250){doc.addPage();y=20}doc.setFontSize(14);doc.setFont(undefined,'bold');doc.text('EDUCATION',20,y);y+=7;for(let i=0;i<dg.length;i++){if(dg[i].value){doc.setFontSize(11);doc.setFont(undefined,'bold');doc.text(dg[i].value,20,y);y+=5;doc.setFont(undefined,'normal');doc.text(`${sc[i].value}${gy[i].value?', '+gy[i].value:''}`,20,y);y+=7}}}const sk=document.getElementById('skills').value;if(sk){if(y>250){doc.addPage();y=20}doc.setFontSize(14);doc.setFont(undefined,'bold');doc.text('SKILLS',20,y);y+=7;doc.setFontSize(10);doc.setFont(undefined,'normal');const sl=doc.splitTextToSize(sk,170);sl.forEach(ln=>{doc.text(ln,20,y);y+=5})}doc.save(`${n.replace(/\s+/g,'_')}_Resume.pdf`)});
document.getElementById('emailBtn').addEventListener('click',()=>{const n=document.getElementById('fullName').value,ph=document.getElementById('phone').value,e=document.getElementById('email').value,s='Resume Submission - '+n,b=`Hello TASK (E&E),\n\nI am submitting my resume for review.\n\nName: ${n}\nPhone: ${ph}\nEmail: ${e}\nBest time to reach me: \n\nI have downloaded my resume as a PDF and will attach it to this email.\n\nThank you!`;window.location.href=`mailto:EandE@trentonsoupkitchen.org?subject=${encodeURIComponent(s)}&body=${encodeURIComponent(b)}`;alert('An email draft has been opened. Please attach your downloaded PDF resume before sending!')});
updateProgress();
</script>
</body>
</html>
