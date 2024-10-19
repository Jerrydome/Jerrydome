- don't import com.twilio.Twilio;
import com.twilio.rest.api.v2010.account.Message;
import com.twilio.type.PhoneNumber;

public class WhatsAppBot {
    // Your Account SID and Auth Token from twilio.com/console
    public static final String ACCOUNT_SID = "your_account_sidimport com.twilio.Twilio;
import com.twilio.rest.api.v2010.account.Message;
import com.twilio.type.PhoneNumber;

public class WhatsAppBot {
    // Your Account SID and Auth Token from twilio.com/console
    public static final String ACCOUNT_SID = "your_account_sid";
    public static final String AUTH_TOKEN = "your_auth_token";

    public static void main(String[] args) {
        Twilio.init(ACCOUNT_SID, AUTH_TOKEN);

        Message message = Message.creator(
                new PhoneNumber("whatsapp:+1234567890"), // To number
                new PhoneNumber("whatsapp:+0987654321"), // From number
                "Hello from your WhatsApp bot!")
            .create();

        System.out.println(message.getSid());
    }
}
